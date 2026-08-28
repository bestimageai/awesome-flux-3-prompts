# FLUX 3 workflow prompts for bestimage.ai

Twelve newly written briefs organized around the four modes described in bestimage.ai's FLUX 3 documentation. The request notes map each mode to its model ID and required media fields. The API host is `https://api.flaq.ai`; see the [integration guide](../docs/bestimage-ai-flux-3-api.md) for usage with a key issued through your bestimage.ai account.

Use only the text inside each prompt block as `prompt`. The request notes specify separate fields, not instructions to paste into the prompt. Use `resolution: "720p"` or `"1080p"` after checking current availability. Replace media inputs with authorized, accessible assets; never put credentials into a prompt.

<a id="text-to-video"></a>
## Text-to-video workflows

[Model page](https://bestimage.ai/models/black-forest-labs/flux-3-text-to-video/) · `model_name: "flux-3.0-text-to-video"` · no media input.

<a id="f01"></a>
## F01 — The key returns home

**Use:** sound-led micro-story  
**Request:** `aspect_ratio: "16:9"`, `duration: 15`, `sound: true`  
**Adjust:** hallway materials, keeping one key and a single sound cue.

```text
A tired adult in a dark blue coat enters a modest hallway carrying one brass key. One small ceramic bowl sits on a narrow shelf. Late-afternoon light, natural contemporary interior.
00:00–00:05 — Locked medium shot from inside the hallway. The person closes the door gently and pauses, holding the key between thumb and forefinger.
00:05–00:10 — Place the key into the bowl. Its small clear ring makes the person relax their shoulders. No other object moves.
00:10–00:15 — They hang the coat on an existing hook and walk out of frame. Hold on the bowl and key for two seconds.
AUDIO: Door latch, one key-on-ceramic ring, coat fabric and quiet room tone. No speech or score.
LOCK: One person, one key, bowl position, hook and consistent sunlight.
AVOID: duplicate keys, an extra ring without contact, bowl changing shape, new rooms, exaggerated emotion, text, logos or watermark.
```

<a id="f02"></a>
## F02 — Two cups, one request

**Use:** concise bilingual service exchange  
**Request:** `aspect_ratio: "9:16"`, `duration: 18`, `sound: true`  
**Adjust:** counter style; retain the assigned dialogue and count.

```text
At a fictional neighborhood café counter, an adult customer faces one barista. Two empty cream cups sit side by side. Both wear plain contemporary clothing.
00:00–00:06 — Stable two-shot. Customer points toward the cups and asks in French, exactly: "On peut s'asseoir près de la fenêtre ?"
00:06–00:12 — Barista looks toward the visible empty window table, then answers in English, exactly: "Of course. That table is free." Wait until the customer has finished.
00:12–00:18 — Customer nods; barista places the same two empty cups on one tray. End before drinks are prepared.
AUDIO: Natural separate voices, two ceramic contacts and low café ambience. No music.
LOCK: One customer, one barista, two cups, one tray and stable eyelines.
AVOID: translating the lines, extra dialogue, appearing drinks, extra cups, automatic subtitles, real venue claims, logos or watermark.
```

<a id="f03"></a>
## F03 — A reflection without a second object

**Use:** basic visual-science illustration  
**Request:** `aspect_ratio: "16:9"`, `duration: 15`, `sound: true`  
**Adjust:** object color; preserve mirror geometry.

```text
Show one red wooden cube on a matte classroom tabletop beside one upright flat mirror. Fixed oblique camera includes the cube, its reflection and the mirror edge.
00:00–00:05 — Hold the cube still with its reflected image aligned plausibly behind the mirror surface.
00:05–00:10 — One adult hand slides the real cube slowly parallel to the mirror, keeping the distance constant. The reflection follows with correct mirrored geometry.
00:10–00:15 — Stop and remove the hand; hold the cube and reflection.
NARRATION: Exact English: "The mirror shows a reflection. There is still only one cube on the table."
AUDIO: Wood sliding and quiet room tone beneath the narration. No music.
LOCK: One cube, one mirror, fixed angle and light.
AVOID: two physical cubes, reflection lag, mirror bending, hand duplicating outside reflection, labels, extra text, logos or watermark.
```

<a id="image-to-video"></a>
## Image-to-video workflows

[Model page](https://bestimage.ai/models/black-forest-labs/flux-3-image-to-video/) · `model_name: "flux-3.0-image-to-video"` · `image_url` is the approved first frame.

<a id="f04"></a>
## F04 — The hinge remains visible

**Use:** eyeglass product interaction  
**Input:** approved first frame with one folded pair and adult hands  
**Request:** `aspect_ratio: "1:1"`, `duration: 12`, `sound: true`  
**Adjust:** only the opening speed.

```text
Start exactly on the supplied frame of one unbranded pair of eyeglasses. Preserve frame color, lens shape, nose pads and the two existing temple hinges.
00:00–00:04 — One hand steadies the bridge while the other grips the folded near temple.
00:04–00:08 — Open that temple through its actual hinge to a natural resting position. Do not bend the frame or move the second temple.
00:08–00:12 — Set the glasses down carefully in their partially open state and withdraw hands. Keep the operated hinge in focus.
AUDIO: Very small hinge friction and soft table contact, quiet studio. No exaggerated click, speech or music.
LOCK: Lens curvature, hinge count, material, scale and table shadow.
AVOID: additional temples, melted lenses, fingerprint disappearance, invented optical claims, logos, price labels or watermark.
```

<a id="f05"></a>
## F05 — The drawn kite breathes

**Use:** animate owned illustration without changing medium  
**Input:** approved drawing of one kite tied to a post  
**Request:** `aspect_ratio: "3:4"`, `duration: 15`, `sound: true`  
**Adjust:** motion amplitude, not artwork design.

```text
Preserve the supplied hand-drawn kite, paper grain, pencil line quality, color patches, string and post. All motion remains visibly two-dimensional on the original sheet.
00:00–00:05 — Locked frame. The kite tilts a few degrees as a drawn breeze lifts its short ribbon tail.
00:05–00:10 — Kite drifts slightly upward until its existing string becomes gently taut. The knot remains tied to the same post.
00:10–00:15 — Breeze eases and the kite returns near its original angle; hold the final paper composition.
AUDIO: Soft paper-texture rustle, not realistic storm wind. No speech or music.
LOCK: One kite, string length, post, original marks and sheet edges.
AVOID: photoreal sky, string detaching, erased pencil texture, additional colors, human drawing hand, added writing, logo or watermark.
```

<a id="f06"></a>
## F06 — The empty tray has a purpose

**Use:** home-product organization concept  
**Input:** approved first frame with tray, keys and phone already visible  
**Request:** `aspect_ratio: "9:16"`, `duration: 18`, `sound: true`  
**Adjust:** product finish only through an updated reference.

```text
Use the supplied first frame of a shallow unbranded wooden entryway tray. One keyring and one plain phone lie beside it. Preserve tray shape, grain, rim height and actual capacity.
00:00–00:06 — Locked close overhead view. One adult hand picks up the keyring and places it in the left side of the tray.
00:06–00:12 — Pick up the existing phone and place it face down on the right, without overlapping or changing scale.
00:12–00:18 — Hand leaves. Camera makes only a slight focus shift toward the tray rim and holds.
AUDIO: Keys on wood, soft phone contact and room tone. No charging sound, voice or music.
LOCK: One tray, one keyring, one phone and the same countertop.
AVOID: wireless-charging implication, extra objects, shifting dividers, phone resizing, invented labels, text, logos or watermark.
```

<a id="start-end-to-video"></a>
## Start/end-frame workflows

[Model page](https://bestimage.ai/models/black-forest-labs/flux-3-start-end-to-video/) · `model_name: "flux-3.0-start-end-to-video"` · `image_url` opens, `image_end_url` closes.

<a id="f07"></a>
## F07 — Closed case, ready instrument

**Use:** endpoint-controlled instrument reveal  
**Inputs:** approved closed and open case frames with identical perspective  
**Request:** `aspect_ratio: "16:9"`, `duration: 18`, `sound: true`  
**Adjust:** opening pace; do not invent instrument parts.

```text
Match the first frame of a closed violin case on a bench and the second frame of that same case open, with the approved violin and bow inside. Camera remains fixed.
00:00–00:06 — Adult hands release the two existing latches separately. Keep both latches attached.
00:06–00:12 — Raise the lid on its visible hinges. The instrument is revealed in its fitted interior, not created during the movement.
00:12–00:18 — Hands leave and the lid rests at the exact end-frame angle. Hold the approved final composition.
AUDIO: Two latch clicks, soft hinge movement and room tone. No violin sound without playing.
LOCK: Case, instrument geometry, bow position, bench and light.
AVOID: extra strings, changing instrument, spontaneous performance, floating lid, new accessories, title copy, logos or watermark.
```

<a id="f08"></a>
## F08 — Set the table for two

**Use:** hospitality arrangement transition  
**Inputs:** matching approved frames, empty table and two-place setting  
**Request:** `aspect_ratio: "16:9"`, `duration: 20`, `sound: true`  
**Adjust:** tableware through both reference frames, not text alone.

```text
Start on the exact empty-table reference and finish on the approved setting for two. The room, table, chairs and camera remain unchanged. All required tableware is carried visibly into frame.
00:00–00:07 — One adult places two plain plates, one at each approved position, using a small tray.
00:07–00:14 — Place two folded napkins and two glasses in the correct positions. Keep each placement distinct; do not add cutlery absent from the end frame.
00:14–00:20 — Carry the empty tray out. Settle on the exact final layout and hold.
AUDIO: Ceramic, glass and fabric contacts with quiet room tone. No speech or score.
LOCK: Two settings, object scale, wood grain, shadows and chair positions.
AVOID: self-setting table, duplicate glass, disappearing tray, elaborate extra décor, meal offers, text, logos or watermark.
```

<a id="f09"></a>
## F09 — Daylight to lamplight

**Use:** controlled lighting transition  
**Inputs:** approved same-room daylight and evening frames  
**Request:** `aspect_ratio: "16:9"`, `duration: 15`, `sound: true`  
**Adjust:** transition pacing; keep architecture fixed.

```text
Use the two supplied frames of the same reading corner. This is an explicit stylized passage-of-time concept, not a real-time sunset. Furniture and camera do not move.
00:00–00:05 — Match the daylight frame. Window illumination begins dimming gradually while the room's existing colors remain stable.
00:05–00:10 — Continue toward the evening exposure. The one existing lamp turns on with a gentle switch click from off screen; do not introduce a person.
00:10–00:15 — Arrive at the approved evening frame, preserving the exact lamp glow and window view. Hold for two seconds.
AUDIO: Continuous quiet interior ambience, one switch click, no time-lapse whoosh or music.
LOCK: Same furniture, lamp, wall junctions, shadows consistent with each light state.
AVOID: seasonal change, moving walls, extra fixtures, flicker, instant global color filter, invented skyline, text, logos or watermark.
```

<a id="video-extend"></a>
## Video-extension workflows

[Model page](https://bestimage.ai/models/black-forest-labs/flux-3-video-extend/) · `model_name: "flux-3.0-video-extend"` · `video_url` is an authorized source clip. Preserve its aspect ratio and check current input limits.

<a id="f10"></a>
## F10 — After the envelope closes

**Use:** continuity-first finishing action  
**Input:** clip ending as a person seals one plain envelope  
**Request:** source `aspect_ratio`, `duration: 10`, `sound: true`  
**Adjust:** final hold length, not the source gesture.

```text
Continue from the source's exact final frame: same hands, just-sealed envelope, desk, pen, clothing, camera and light. Do not repeat the sealing action.
00:00–00:04 — Finish the existing pressure along the flap, then lift the hand naturally. The envelope stays closed.
00:04–00:07 — Turn the envelope face up and place it in the clear desk space already visible. No address is generated.
00:07–00:10 — Put the existing pen beside it and withdraw hands. Hold the still arrangement.
AUDIO: Continue source room tone; add paper sliding and one pen contact, matching acoustic distance.
LOCK: Envelope dimensions, flap state, pen, hands and direction of movement.
AVOID: starting a new letter, reopening the envelope, new stamps, camera cut, disappearing ink tool, extra voice, labels or watermark.
```

<a id="f11"></a>
## F11 — Let the curtain settle

**Use:** extend an architectural ambience shot  
**Input:** source clip ending with a curtain moving in a gentle breeze  
**Request:** source `aspect_ratio`, `duration: 12`, `sound: true`  
**Adjust:** only the breeze decay and ending hold.

```text
Continue the original curtain motion from its exact final position and velocity. Preserve window geometry, fabric weave, rod, floor, furniture, outside view, camera and exposure.
00:00–00:05 — The existing breeze weakens gradually. Curtain folds make one smaller return swing, responding as a single piece of fabric.
00:05–00:09 — Motion settles further until only the hem moves slightly. Do not close the window or introduce a hand.
00:09–00:12 — Hold a nearly still end frame suitable for a clean cut.
AUDIO: Carry over the source ambience and cloth rustle, fading only the movement-related sound. Do not add new birds, speech or score.
LOCK: Fabric length, fold pattern, window state and source lighting.
AVOID: resetting the oscillation, curtain multiplying, changed weather, new furniture, exposure jump, hidden dissolve, text or watermark.
```

<a id="f12"></a>
## F12 — Return the tool to its place

**Use:** workshop continuation with object-state control  
**Input:** clip ending after tightening a small wooden object's final screw  
**Request:** source `aspect_ratio`, `duration: 15`, `sound: true`  
**Adjust:** ending composition within the existing workspace.

```text
Start from the source clip's exact final frame. Preserve hands, screwdriver, completed screw position, wooden object, parts tray, workbench, camera and sound. No new assembly step.
00:00–00:05 — Withdraw the screwdriver along the screw axis and lay it in the already visible empty part of the tray.
00:05–00:10 — Lift the wooden object gently and rotate it only enough to inspect the finished edge. Do not reveal a new mechanism or claim a load test.
00:10–00:15 — Set the object back at its source position, remove both hands and hold.
AUDIO: Source room tone, tool on tray, fingers on wood and final set-down. No new dialogue or music.
LOCK: Screw count, object geometry, tool, tray position and natural hand contact.
AVOID: repeated tightening, extra hardware, self-moving tool, changed grain, camera jump, safety certification, captions, logos or watermark.
```

## Adaptation checklist

1. Choose the mode from the actual input asset, not the desired marketing label.
2. Copy the complete prompt; put model, duration, sound and media values in their own request fields.
3. Check prompt length and current API limits before submitting. Do not silently truncate a recipe.
4. A target endpoint or continuity lock is a request to the model, not a guarantee.
5. Track the returned task ID. Do not blindly resubmit a paid job after a timeout.
6. Review first/last frames, timing, language, source rights and final disclosure.
