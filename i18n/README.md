# FLUX 3 language directory

The bestimage.ai team maintains 84 canonical English recipes and a focused shared-scene set in 11 other languages. Each locale contains three complete translated prompts, not the complete library.

## Landing pages

[English](../README.md) · [简体中文](../README_zh-CN.md) · [日本語](../README_ja-JP.md) · [Español](../README_es-ES.md)

## Shared scenes

| Locale ID | English canonical source | What stays identical |
| --- | --- | --- |
| I18N-01 | [X01 — One useful sentence](../prompts/social-experimental.md#x01) | 15-second scene, 5-second silence, microphone and notebook |
| I18N-02 | [E01 — Two dividers, one place](../prompts/ecommerce-product.md#e01) | 20-second sequence, 3 product parts, 2 slots, notebook prop |
| I18N-03 | [L01 — Move the card, not the light](../prompts/education-science.md#l01) | 15-second sequence, fixed lamp/screen, card closer and shadow larger |

Only directing language and exact speech change. Scene IDs are translation identifiers, not new canonical prompt IDs.

| Language | File | Translated scenes |
| --- | --- | ---: |
| 简体中文 | [zh-CN](zh-CN.md) | 3 |
| 日本語 | [ja-JP](ja-JP.md) | 3 |
| Español | [es-ES](es-ES.md) | 3 |
| Français | [fr-FR](fr-FR.md) | 3 |
| Deutsch | [de-DE](de-DE.md) | 3 |
| 한국어 | [ko-KR](ko-KR.md) | 3 |
| Português do Brasil | [pt-BR](pt-BR.md) | 3 |
| Italiano | [it-IT](it-IT.md) | 3 |
| العربية | [ar](ar.md) | 3 |
| Русский | [ru-RU](ru-RU.md) | 3 |
| Bahasa Indonesia | [id-ID](id-ID.md) | 3 |

## Model and image-workflow entries

The linked model pages below use the verified English landing URLs consistently across all repository languages. The repository does not imply that an English API guide has been translated merely because a localized README links to it.

- [FLUX 3 text to video](https://bestimage.ai/models/black-forest-labs/flux-3-text-to-video/): a new scene from text.
- [FLUX 3 image to video](https://bestimage.ai/models/black-forest-labs/flux-3-image-to-video/): one approved first frame.
- [FLUX 3 start/end to video](https://bestimage.ai/models/black-forest-labs/flux-3-start-end-to-video/): two required endpoint frames.
- [FLUX 3 video extend](https://bestimage.ai/models/black-forest-labs/flux-3-video-extend/): continuation from a clip.
- [GPT Image 2 API](https://bestimage.ai/models/openai/gpt-image-2/): separate still-image preparation; not a video endpoint.

The [API integration guide](../docs/bestimage-ai-flux-3-api.md) uses `https://api.flaq.ai`, the API host for bestimage.ai. Use an API key issued through your bestimage.ai account.

## Translation review

Preserve timing, camera, prop counts, science and exclusions. Translate labels as well as prose. Use natural local-language dialogue without unrequested subtitles or mixed-language filler. Have a fluent reviewer check the final audio and generated text before publication. Do not label these text translations as speech-model benchmarks.

[Source and license notes](../docs/sources.md) · [Contributing](../CONTRIBUTING.md)
