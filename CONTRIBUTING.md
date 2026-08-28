# Contributing original FLUX 3 prompts

Thank you for improving the collection. Contributions should make the library more useful without importing someone else's wording, identity, or media.

## What a prompt submission needs

- A new scene concept and an original title.
- A practical use case and intended aspect ratio/duration.
- A timeline with readable shot or action beats.
- Identity, wardrobe, object, geography, and lighting continuity rules.
- An audio plan, even when the correct plan is deliberate silence.
- Exact dialogue or typography in quotation marks, with language named.
- A short avoid list for likely artifacts.
- Rights and consent for every supplied reference image, voice, logo, or recognizable person.

## Style

Write concrete, visible instructions. Prefer “the camera tracks beside the bicycle at wheel height” to “dynamic cinematic camera.” Keep one primary action in each time range. Do not claim a prompt was tested unless you can provide the settings and output evidence.

## Originality checklist

Before opening a contribution, confirm that:

1. The title, description, narrative beats, copy, and prompt wording are newly written.
2. The contribution does not contain scraped author profiles, unrelated promotional calls to action, or third-party gallery branding. Preserve necessary source links, applicable license notices and author attribution for adopted or adapted material.
3. Any inspiration is transformed into a distinct subject, setting, structure, and creative execution.
4. Preview media is original or correctly licensed, and its status is described honestly.
5. No generated preview is represented as official FLUX 3 output or a benchmark result.

## File placement

Add the prompt to the most relevant file in `prompts/`. Use a unique stable ID and explicit lowercase anchor (for example, `C07` and `c07`). Keep the existing heading format and increment the prompt count only after the new entry is complete. Translations should preserve meaning and exact quoted dialogue rather than introducing new story beats.

Also update:

- `prompts/README.md` with the pack, ID, starting asset, and business-goal references;
- `docs/use-case-matrix.md` when the prompt fills a new decision path;
- the prompt and pack counts in `README.md` and localized landing pages;
- local links and headings affected by the new entry.

## Localization contributions

The English canonical library defines distinct concepts. Locale files in `i18n/` translate shared test scenes and are not counted as new concepts.

A localization must:

1. Preserve the `I18N-##` scene ID, time ranges, camera, object count, physical behavior, and exclusions.
2. Translate the directing language naturally rather than copying English word order.
3. Localize exact speech for the named region and keep it in quotation marks.
4. Preserve scientific meaning and safety caveats.
5. Avoid stereotypes, invented brand references, automatic subtitles, or new story beats.
6. Have spelling, punctuation, pronunciation intent, and generated glyphs reviewed by a fluent speaker before being marked production-ready.

Add new languages to `i18n/README.md`. A language is listed as supported only after all three shared scenes are complete.

## Validation before submission

- All relative Markdown links resolve.
- The canonical prompt count matches the numbered headings in `prompts/*.md`, excluding `prompts/README.md`.
- Every supported non-English locale contains `I18N-01`, `I18N-02`, and `I18N-03` exactly once.
- No preview asset is left only in a temporary generation directory.
- There are no unrelated author profiles, promotional links or third-party gallery identifiers. Necessary attribution and license notices remain intact.
- Code fences, explicit scene anchors, image paths and relative links are valid; Markdown hard line breaks are preserved.
- No request example claims API execution or compatible credentials without evidence.
