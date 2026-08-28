# FLUX 3 prompting guide: from idea to usable shot

Maintained by the bestimage.ai team. FLUX 3 prompts work best as compact directing briefs. This guide turns a vague idea into a testable prompt without pretending that prompt text alone replaces production judgment.

The [84-scene index](../prompts/README.md) contains creative specifications, not model-tested results.

## 1. Choose the generation mode before writing

| You already have | Use this strategy | Lock first |
| --- | --- | --- |
| Only an idea or script | Text-to-video | world, subject description, timeline |
| A product, person, illustration, or first frame | Image-to-video | identity, geometry, composition, light |
| Several images with different jobs | Multi-reference | one role per image; reject cross-contamination |
| Required visual milestones | Ordered keyframes | exact order, target times, invariant geometry |
| A clip whose action should continue | Video continuation | final frame, momentum, camera, exposure, audio bed |
| A clip whose style or context should change | Video-to-video | source elements to preserve vs transform |

The table describes creative input strategies, not interchangeable API parameters. bestimage.ai's documented FLUX 3 modes expose text, one first-frame image, start/end images, and video extension. Its single `image_url` field does not establish support for arbitrary identity/style/reference arrays. Multi-reference and ordered multi-keyframe strategies above require an interface that explicitly supports them. For this edition's bestimage.ai recipes, prepare one approved composite first frame or a matched pair of endpoints; never invent extra request fields.

Do not ask every reference to control everything. A useful role statement looks like this:

```text
Image 1 controls identity and wardrobe only.
Image 2 controls environment, time of day, and palette only.
Clip 1 controls camera path and movement timing only.
Do not import people, text, logos, or props from style and motion references.
```

## 2. Define the end frame early

The last three to five seconds determine whether a clip is editable. Decide whether the ending should:

- hold a product hero angle;
- settle on a readable title;
- provide negative space for post-production copy;
- match the start frame for a loop;
- preserve motion for continuation;
- stop in silence for an editorial cut.

If the final frame matters, describe camera deceleration, subject behavior, prop state, and hold duration. “End cinematically” is not actionable.

## 3. Write a readable timeline

Each time range should contain one main action and one camera intention. A practical 20-second structure is:

```text
00:00-00:05 — Establish the world and subject.
00:05-00:12 — Perform the primary action with visible cause and effect.
00:12-00:16 — Introduce a turn, response, or proof point.
00:16-00:20 — Decelerate into a deliberate final frame.
```

Avoid packing dialogue, camera orbit, costume change, object transformation, weather change, and title animation into the same four seconds.

## 4. Separate camera, subject, and environment motion

Write these as three independent layers:

```text
Camera: track backward at walking speed, chest height, never cross the action axis.
Subject: walk forward, open the umbrella once, then keep it open.
Environment: rain falls at a constant angle; trees and coat respond to the same crosswind.
```

This makes failures easier to diagnose. If a result feels unstable, remove one motion layer before adding adjectives.

## 5. Lock identity and product geometry

List only details that are visible and important:

- facial structure, age, hair, distinctive mark;
- body proportions and handedness;
- wardrobe layers, color, fasteners, accessories;
- product silhouette, part count, label area, fill level, material;
- object scale relative to hands and environment.

Repeat the lock after any major style change. Avoid vague instructions such as “keep everything the same.”

## 6. Prompt physical causality

Strong video feels causal: force precedes motion, sound follows impact, weight affects acceleration, and wetness accumulates instead of resetting.

Check:

- hands touch an object before it moves;
- wheels rotate at the distance traveled;
- liquid level, spill, and reflection remain consistent;
- cloth, hair, dust, and plants respond to the same wind;
- shadows and reflections share one light source;
- props stay where they were placed;
- the camera cannot pass through walls or people.

## 7. Design audio as four layers

```text
Dialogue: exact quoted words, language, voice character, pace, pauses.
Ambience: the continuous acoustic space.
Foley: visible causes—footsteps, fabric, tools, doors, water.
Music: instrument, tempo, entry, exit, and intensity; or explicitly none.
```

For multilingual speech, state what must not happen:

```text
Speak the quoted Japanese line exactly once.
Do not translate, paraphrase, repeat, subtitle, or add words.
Natural conversational delivery; no announcer cadence.
```

## 8. Decide whether text belongs in generation

Generate text when it is visually central and short: a title, label, chapter card, or sign that interacts with the scene. Add text in post when it is legally sensitive, frequently updated, data-heavy, price-based, or needs exact brand typography.

When generating text:

```text
Render exactly once: "SEE IT. SOLVE IT."
Warm-white geometric sans serif, centered, stable for three seconds.
No extra words, translation, punctuation, logo, or decorative glyphs.
```

## 9. Build a useful avoid list

An avoid list should target likely failures, not repeat generic quality language.

Useful:

```text
Avoid: duplicate bottle, changing liquid level, cap drift, invented label,
warped reflection, extra copy, logo, watermark.
```

Less useful:

```text
Avoid: bad quality, ugly, mistakes, low resolution.
```

## 10. Iterate with one controlled change

Use a simple record:

| Version | Changed | Kept fixed | Result | Next decision |
| --- | --- | --- | --- | --- |
| v1 | baseline | — | identity good; camera too fast | slow camera only |
| v2 | camera speed | identity, action, audio | stable; end frame short | add 3-second hold |
| v3 | end hold | everything else | usable | render final |

Do not rewrite the whole prompt after every result. One-change iteration preserves what already works.

## 11. Production review checklist

- The concept is original or properly licensed.
- Every reference has a declared role and usage rights.
- Identity, voice, logo, and location permissions are documented.
- Visible claims are supportable; medical, financial, and performance claims are reviewed.
- Dialogue, captions, and typography match the intended locale.
- Physics, continuity, hands, text, and reflections are reviewed frame by frame.
- Generated content is not presented as documentary evidence or an official benchmark.
- A human approves the final edit, audio mix, and release context.

## 12. Access and parameters

FLUX 3 capabilities, endpoints, duration, resolution bands, pricing, and available input modes may change during rollout. Use the [official FLUX 3 model page](https://bfl.ai/models/flux-3) and [official overview](https://bfl.ai/blog/flux-3) as the source of truth rather than copying old API examples into production.

## 13. Prepare still references with GPT Image 2

The [bestimage.ai GPT Image 2 API page](https://bestimage.ai/models/openai/gpt-image-2/) is a separate image workflow. Use it to explore storyboard compositions or revise an authorized still, then inspect identity, product geometry, object count and rights before using that image in a FLUX 3 video request. A generated image is not proof of a real product, venue, event or a successful video workflow.

For two endpoints, prepare compatible camera position, perspective, object inventory and lighting. If the desired action cannot plausibly connect them, revise the brief before spending on video generation.

## 14. Match request constraints without changing the brief silently

Use a supported ratio and duration when authoring the scene; these recipes use the documented 5–20 second range and selected supported ratios. Inspect current limits at submission time. A creative cadence such as stop motion is not an `fps` parameter. A requested endpoint match is not a promise of exact pixels.

Copy the full prompt, measure its length and preserve all role, dialogue and continuity instructions. If a provider limit prevents submission, revise deliberately; do not truncate the prompt automatically. Keep model IDs and source URLs outside the natural-language prompt.
