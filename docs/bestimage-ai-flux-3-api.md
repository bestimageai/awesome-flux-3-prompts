# FLUX 3 API integration on bestimage.ai

> [!NOTE]
> **Use `https://api.flaq.ai` for the bestimage.ai API.** Authenticate with an API key issued through your bestimage.ai account. This guide covers submission, polling, error handling and credential safety.
>
> The [bestimage.ai workflow briefs](../prompts/bestimage-api-workflows.md) map creative scenes to the four video modes below. [GPT Image 2](https://bestimage.ai/models/openai/gpt-image-2/) is a separate still-image preparation entry, not a FLUX 3 video endpoint.

## About this bestimage.ai edition

The [bestimage.ai](https://bestimage.ai/) team maintains this prompt library and its practical scene-to-request guidance. Its scope is to help creators choose a documented video mode, prepare authorized inputs and review outputs without confusing creative intentions with verified results.

The current bestimage.ai entries are [text to video](https://bestimage.ai/models/black-forest-labs/flux-3-text-to-video/), [image to video](https://bestimage.ai/models/black-forest-labs/flux-3-image-to-video/), [start/end to video](https://bestimage.ai/models/black-forest-labs/flux-3-start-end-to-video/) and [video extend](https://bestimage.ai/models/black-forest-labs/flux-3-video-extend/).

## Integration scope and source

This guide covers request submission, task polling, error handling and API key security for bestimage.ai.

## Choose the right FLUX 3 endpoint

All four modes use the same task endpoints. The `model_name` and source-media fields determine the workflow.

| Workflow | `model_name` | Required source field(s) | Best for |
| --- | --- | --- | --- |
| [Text to video](https://bestimage.ai/models/black-forest-labs/flux-3-text-to-video/) | `flux-3.0-text-to-video` | none | new scenes, concept films, explainers, ads, multilingual dialogue |
| [Image to video](https://bestimage.ai/models/black-forest-labs/flux-3-image-to-video/) | `flux-3.0-image-to-video` | `image_url` | animating a product shot, character frame, key visual, or artwork |
| [Video extend](https://bestimage.ai/models/black-forest-labs/flux-3-video-extend/) | `flux-3.0-video-extend` | `video_url` | continuing action, lengthening a scene, or creating a follow-on beat |
| [Start and end frames to video](https://bestimage.ai/models/black-forest-labs/flux-3-start-end-to-video/) | `flux-3.0-start-end-to-video` | `image_url`, `image_end_url` | controlled transitions, product reveals, before/after motion, matched endpoints |

## Recommended API by production goal

The four video modes share bearer authentication, an asynchronous task endpoint and a polling response shape. The following mapping connects production goals to the documented bestimage.ai modes..

| Production need | Recommended API | Why | Ready-made prompts |
| --- | --- | --- | --- |
| Explore an original scene from a brief | [Text to Video](https://bestimage.ai/models/black-forest-labs/flux-3-text-to-video/) | no source asset required; prompt controls action, camera, sound, dialogue, and world | [F01–F03](../prompts/bestimage-api-workflows.md#text-to-video) |
| Preserve a product, person, artwork, or first composition | [Image to Video](https://bestimage.ai/models/black-forest-labs/flux-3-image-to-video/) | `image_url` anchors visible identity and geometry while the prompt directs motion | [F04–F06](../prompts/bestimage-api-workflows.md#image-to-video) |
| Land on a designed final frame | [Start/End to Video](https://bestimage.ai/models/black-forest-labs/flux-3-start-end-to-video/) | separate start and end images provide stronger endpoint control than text alone | [F07–F09](../prompts/bestimage-api-workflows.md#start-end-to-video) |
| Continue a source clip's momentum and scene state | [Video Extend](https://bestimage.ai/models/black-forest-labs/flux-3-video-extend/) | `video_url` carries the existing visual and motion context into the next beat | [F10–F12](../prompts/bestimage-api-workflows.md#video-extend) |

Start with text-to-video only when no owned source asset must survive. If identity or object geometry matters, prefer image-to-video. If both editorial endpoints matter, supply both frames. If the source already contains the desired motion, exposure, camera path, and ambience, extend it instead of attempting to reconstruct those conditions in a fresh generation.

### Shared endpoints

```text
POST https://api.flaq.ai/api/v1/video/task
GET  https://api.flaq.ai/api/v1/video/{task_id}
```

Authenticate with a server-side API key:

```http
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

Never expose an API key in a browser bundle, public repository, prompt, or client-side mobile application. Route production requests through a trusted backend and load the key from an environment variable or secrets manager.

## One reusable JavaScript client

This Node.js example submits any of the four workflows, validates HTTP responses, handles failed tasks, and applies a polling timeout.

```js
const API_BASE = 'https://api.flaq.ai/api/v1/video';
const API_KEY = process.env.BESTIMAGE_API_KEY;

if (!API_KEY) throw new Error('Set BESTIMAGE_API_KEY before running this script.');

const authHeaders = {
  Authorization: `Bearer ${API_KEY}`,
  'Content-Type': 'application/json',
};

async function readJson(response) {
  const payload = await response.json();
  if (!response.ok) {
    const message = payload?.message || payload?.data?.task_status_msg;
    throw new Error(message || `bestimage.ai API returned HTTP ${response.status}`);
  }
  return payload;
}

async function submitVideoTask(input) {
  const response = await fetch(`${API_BASE}/task`, {
    method: 'POST',
    headers: authHeaders,
    body: JSON.stringify(input),
  });

  const payload = await readJson(response);
  if (!payload?.data?.task_id) throw new Error('Response did not include data.task_id.');
  return payload.data.task_id;
}

async function waitForVideo(taskId, options = {}) {
  const intervalMs = options.intervalMs ?? 10_000;
  const timeoutMs = options.timeoutMs ?? 20 * 60_000;
  const deadline = Date.now() + timeoutMs;

  while (Date.now() < deadline) {
    const response = await fetch(`${API_BASE}/${encodeURIComponent(taskId)}`, {
      headers: { Authorization: `Bearer ${API_KEY}` },
    });
    const payload = await readJson(response);
    const status = payload?.data?.task_status;

    if (status === 'succeed') {
      const videoUrl = payload?.data?.task_result?.videos?.[0]?.url;
      if (!videoUrl) throw new Error('Task succeeded without a video URL.');
      return videoUrl;
    }

    if (status === 'failed') {
      throw new Error(payload?.data?.task_status_msg || 'Video generation failed.');
    }

    await new Promise((resolve) => setTimeout(resolve, intervalMs));
  }

  throw new Error(`Timed out while waiting for task ${taskId}.`);
}

async function generateVideo(input) {
  const taskId = await submitVideoTask(input);
  console.log('Task:', taskId);
  return waitForVideo(taskId);
}
```

## Request examples for all four modes

Use one of these request objects with `generateVideo(request)`.

### 1. Text to video

```js
const request = {
  model_name: 'flux-3.0-text-to-video',
  prompt: `A rain-soaked night market seen in one slow tracking shot.
A bicycle courier stops at a noodle stall while steam crosses warm practical light.
Natural motion, stable identity, realistic reflections and native street ambience.`,
  resolution: '1080p',
  aspect_ratio: '16:9',
  duration: 10,
  sound: true,
};

console.log(await generateVideo(request));
```

### 2. Image to video

```js
const request = {
  model_name: 'flux-3.0-image-to-video',
  image_url: 'https://cdn.example.com/product-hero.jpg',
  prompt: `Preserve the exact bottle geometry, label, liquid level, and lighting.
The camera makes a slow 90-degree orbit while a single water droplet travels down the glass.
Keep the product centered and end on a clean, readable hero frame.`,
  resolution: '1080p',
  aspect_ratio: '16:9',
  duration: 10,
  sound: true,
};

console.log(await generateVideo(request));
```

### 3. Video extend

```js
const request = {
  model_name: 'flux-3.0-video-extend',
  video_url: 'https://cdn.example.com/source-scene.mp4',
  prompt: `Continue directly from the source clip's final state.
The subject walks toward the skyline as the camera keeps the same direction, speed, lens character,
lighting, wardrobe, and environmental ambience. Do not reset the action or introduce a new location.`,
  resolution: '1080p',
  aspect_ratio: '16:9',
  duration: 10,
  sound: true,
};

console.log(await generateVideo(request));
```

### 4. Start and end frames to video

```js
const request = {
  model_name: 'flux-3.0-start-end-to-video',
  image_url: 'https://cdn.example.com/start-frame.jpg',
  image_end_url: 'https://cdn.example.com/end-frame.jpg',
  prompt: `Create one physically plausible transition between the supplied frames.
Use a slow forward dolly, preserve the subject's identity and screen position,
match the lighting change gradually, and arrive at the final frame without a last-second morph.`,
  resolution: '720p',
  aspect_ratio: '16:9',
  duration: 8,
  sound: true,
};

console.log(await generateVideo(request));
```

Browse this edition's twelve newly written briefs in the [bestimage.ai workflow pack](../prompts/bestimage-api-workflows.md). Review required input URLs and current mode limits before running any example; generation can consume account credits.

## Python quickstart

This dependency-light example uses `requests`, preserves the task ID, checks HTTP failures, and stops after a bounded timeout.

```python
import os
import time
import requests

API_BASE = "https://api.flaq.ai/api/v1/video"
API_KEY = os.environ["BESTIMAGE_API_KEY"]
HEADERS = {
    "Authorization": f"Bearer {API_KEY}",
    "Content-Type": "application/json",
}


def submit_video_task(payload):
    response = requests.post(
        f"{API_BASE}/task",
        headers=HEADERS,
        json=payload,
        timeout=60,
    )
    response.raise_for_status()
    body = response.json()
    task_id = body.get("data", {}).get("task_id")
    if not task_id:
        raise RuntimeError("Response did not include data.task_id")
    return task_id


def wait_for_video(task_id, interval_seconds=10, timeout_seconds=1200):
    deadline = time.monotonic() + timeout_seconds
    while time.monotonic() < deadline:
        response = requests.get(
            f"{API_BASE}/{task_id}",
            headers={"Authorization": f"Bearer {API_KEY}"},
            timeout=60,
        )
        response.raise_for_status()
        body = response.json()
        data = body.get("data", {})
        status = data.get("task_status")

        if status == "succeed":
            videos = data.get("task_result", {}).get("videos", [])
            if not videos or not videos[0].get("url"):
                raise RuntimeError("Task succeeded without a video URL")
            return videos[0]["url"]
        if status == "failed":
            raise RuntimeError(data.get("task_status_msg") or "Generation failed")

        time.sleep(interval_seconds)

    raise TimeoutError(f"Timed out while waiting for task {task_id}")


payload = {
    "model_name": "flux-3.0-text-to-video",
    "prompt": "A dawn ferry crossing with realistic wake, slow camera drift, and synchronized harbor ambience.",
    "resolution": "1080p",
    "aspect_ratio": "16:9",
    "duration": 10,
    "sound": True,
}

task_id = submit_video_task(payload)
print("Task:", task_id)
print("Video:", wait_for_video(task_id))
```

## cURL quickstart

```bash
curl --request POST \
  --url https://api.flaq.ai/api/v1/video/task \
  --header "Authorization: Bearer $BESTIMAGE_API_KEY" \
  --header "Content-Type: application/json" \
  --data '{
    "model_name": "flux-3.0-text-to-video",
    "prompt": "A quiet cinematic dawn over a working harbor, slow lateral camera move, realistic water and synchronized native ambience.",
    "resolution": "1080p",
    "aspect_ratio": "16:9",
    "duration": 10,
    "sound": true
  }'
```

Then poll with the returned `data.task_id`:

```bash
curl --request GET \
  --url "https://api.flaq.ai/api/v1/video/YOUR_TASK_ID" \
  --header "Authorization: Bearer $BESTIMAGE_API_KEY"
```

The documented terminal states are:

- `succeed` — read `data.task_result.videos[0].url`.
- `failed` — inspect `data.task_status_msg`.
- Any other status — continue polling with a sensible delay.

## Map repository prompts to API fields

The long-form prompts in this repository deliberately separate creative direction from changing API settings.

| Prompt recipe field | API destination |
| --- | --- |
| `WORLD`, `SUBJECT LOCK`, `VISUAL LANGUAGE`, `TIMELINE` | combine into `prompt` |
| `AUDIO`, dialogue, Foley, ambience | keep inside `prompt` and set `sound: true` when supported |
| `AVOID`, continuity constraints, exact text | keep inside `prompt` |
| `FORMAT` aspect ratio | `aspect_ratio` |
| `FORMAT` duration | `duration` |
| desired output size | `resolution` |
| first image or identity frame | `image_url` for image-driven modes |
| target final frame | `image_end_url` for start/end mode |
| source clip to continue | `video_url` for video extend |

## Production checklist

1. **Host inputs on reachable HTTPS URLs.** Confirm that the API service can fetch the asset and that temporary signed URLs will not expire during processing.
2. **Match the mode to the source.** Do not describe an end frame only in text when start/end mode can supply it directly.
3. **Preserve source geometry.** For image-to-video and start/end workflows, explicitly lock identity, product shape, lighting direction, screen position, and details that must not drift.
4. **Continue, do not restart.** A video-extension prompt should describe the next beat and the invariants inherited from the source clip.
5. **Use causal audio direction.** Name visible sound sources, spoken language, exact dialogue, ambience, Foley, and intentional silence.
6. **Design for retries.** Store the task ID, use bounded polling, surface provider error messages, and avoid submitting duplicate paid jobs after a client timeout.
7. **Download and archive deliberately.** Provider URLs may be delivery URLs rather than permanent storage; move approved outputs into your own media pipeline.
8. **Review rights and safety.** Use only authorized source media, likenesses, voices, brands, music, and claims.

## Live references

- [Model resources and image notes](sources.md)
- [FLUX 3 text-to-video API](https://bestimage.ai/models/black-forest-labs/flux-3-text-to-video/)
- [FLUX 3 image-to-video API](https://bestimage.ai/models/black-forest-labs/flux-3-image-to-video/)
- [FLUX 3 video-extend API](https://bestimage.ai/models/black-forest-labs/flux-3-video-extend/)
- [FLUX 3 start/end-to-video API](https://bestimage.ai/models/black-forest-labs/flux-3-start-end-to-video/)
- [bestimage.ai FLUX 3 documentation](https://bestimage.ai/docs/?page=api%2Fflux-3)
