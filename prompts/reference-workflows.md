# FLUX 3 reference-driven prompts

Six briefs for the four documented bestimage.ai video modes. A single first-frame image is not an arbitrary multi-reference input. Prepare and approve combined visual references before using image-to-video; do not invent unsupported request fields.

<a id="r01"></a>
## R01 — The portrait holds its person

**Use:** identity-preserving portrait movement · **Mode:** image to video  
**Input:** one authorized portrait first frame containing the complete intended setting  
**Format:** 9:16, 12 seconds · **Adjust:** gesture size, not identity.

```text
Begin exactly from the supplied portrait. Preserve the adult subject's face, age, hair, skin texture, clothing and background. Keep camera height and focal length unchanged.
00:00–00:04 — Hold a relaxed pose with subtle breathing. The subject looks toward the same off-camera point as in the source.
00:04–00:08 — Subject blinks once, turns their head only slightly toward the camera and lets the shoulders follow naturally.
00:08–00:12 — Settle into a quiet neutral expression and hold. No smile enlargement or beauty retouching.
AUDIO: Low room ambience appropriate to the visible setting. No speech or music.
LOCK: Facial proportions, hairline, glasses if present, garment seams, light direction and background objects.
AVOID: de-aging, smoothing skin, changed eye color, new jewelry, hand entering from nowhere, background replacement, text, logos or watermark.
```

<a id="r02"></a>
## R02 — A book opens to its endpoint

**Use:** start/end composition control · **Mode:** start/end to video  
**Input:** matching approved frames of the same book closed and open  
**Format:** 16:9, 15 seconds · **Adjust:** book design only in both endpoints together.

```text
Image 1 is the exact closed-book starting frame; Image 2 is the same book open at its approved spread, with identical desk and camera. Keep page content as supplied, not newly invented readable text.
00:00–00:05 — Hold Image 1. One adult hand enters from the near edge and touches the front cover.
00:05–00:11 — Lift the cover and open the book smoothly toward the target spread. Use only a small plausible group of pages; do not flip through hundreds.
00:11–00:15 — Hand settles the page, leaves the frame and the image reaches the exact final composition. Hold the last two seconds.
AUDIO: Cover movement, paper and quiet room tone.
LOCK: Spine, cover corners, desk grain, page dimensions, light and one hand.
AVOID: book morphing, new illustrations, page-count explosion, unmotivated camera movement, dissolving cover, extra hands, logos or watermark.
```

<a id="r03"></a>
## R03 — Finish the same pour

**Use:** continuation of an existing action · **Mode:** video extend  
**Input:** authorized source clip ending during a gentle water pour  
**Format:** source ratio, 10 added seconds · **Adjust:** final hold, not source state.

```text
Continue exactly from the source clip's final frame. Preserve the adult hands, tilted pitcher, receiving glass, current water levels, stream direction, tabletop, camera and exposure.
00:00–00:04 — Continue the existing pour briefly at the same rate, then rotate the pitcher upright before the glass becomes too full. Keep fluid volume plausible.
00:04–00:07 — Set the pitcher down in the empty space already visible. Do not shift the glass.
00:07–00:10 — Hands withdraw. Hold on the water settling, with one consistent reflection and quiet ending.
AUDIO: Carry over the source room tone and pouring sound, fading naturally when the stream stops. Add only the pitcher set-down.
LOCK: Exact initial motion, hand positions, object geometry and light. No new shot.
AVOID: restarting the pour, full glass resetting, pitcher changing hand, liquid clipping, source music replaced, extra glass, labels or watermark.
```

<a id="r04"></a>
## R04 — Animate the approved composite

**Use:** separate identity and environment preparation · **Mode:** image to video  
**Input:** one final approved composite, not separate API reference slots  
**Format:** 16:9, 15 seconds · **Adjust:** motion after approving the combined still.

```text
Use the supplied approved still of one original illustrated character standing in a paper-cut garden. Identity and setting have already been combined into this single first frame. Preserve both.
00:00–00:05 — Locked medium-wide view. The character looks at one existing paper flower. Only a slight breeze moves the flower stem.
00:05–00:10 — Character leans forward a little, staying within the original footprint, and raises one open hand without touching or picking the flower.
00:10–00:15 — Character returns to the starting pose. The flower settles and all material remains visibly cut paper.
AUDIO: Soft paper rustle and a restrained tabletop ambience; no dialogue or music.
LOCK: Character face, costume, paper edges, flower count, garden layout and palette.
AVOID: importing new subjects, changing to photorealism, adding reference slots, extra flowers, floating character, text, logos or watermark.
```

<a id="r05"></a>
## R05 — Two endpoints, one practical action

**Use:** controlled workstation reset · **Mode:** start/end to video  
**Input:** approved start/end stills, identical camera and object inventory  
**Format:** 16:9, 20 seconds · **Adjust:** layout only within reachable positions.

```text
The first frame shows one sketchbook, one pencil and one closed pencil case on a desk. The end frame shows the same sketchbook centered, pencil inside the closed case and case beside the book. Preserve the desk and window.
00:00–00:06 — Two adult hands enter. Center the sketchbook with one gentle slide; its pages remain closed.
00:06–00:14 — Open the existing case, place the pencil inside and close it. Keep the zipper path visible; no jump cut hides the action.
00:14–00:20 — Move the case to the exact end-frame position and withdraw hands. Match the final composition and hold.
AUDIO: Paper sliding, zipper, pencil contact and continuous room tone. No score.
LOCK: Same three objects, constant light, camera and surface texture.
AVOID: vanishing pencil, added stationery, self-closing zipper, perspective change, interior redesign, generated text, logos or watermark.
```

<a id="r06"></a>
## R06 — Respect the unseen side

**Use:** conservative single-view product animation · **Mode:** image to video  
**Input:** authorized front three-quarter photograph of the product  
**Format:** 1:1, 12 seconds · **Adjust:** small camera arc only.

```text
Preserve the supplied product exactly. The reference only establishes its visible front and one side, so do not invent the rear, hidden controls, connectors or internal parts.
00:00–00:04 — Hold the reference composition with subtle natural focus settling.
00:04–00:08 — Move the camera through a very small arc toward the already visible side, stopping before an unseen face would be revealed. The object stays stationary.
00:08–00:12 — Return gently toward the original angle and hold a clean final frame.
AUDIO: Quiet studio room tone only. No operating sounds or voice.
LOCK: All visible silhouette details, markings, seams, materials, shadow and scale.
TEXT: Preserve only text genuinely supplied in the source; introduce none.
AVOID: full turntable rotation, invented ports, transparent shell, new buttons, product-performance claims, unsupported dimensions, extra products or watermark.
```
