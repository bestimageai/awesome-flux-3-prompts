<p align="center">
  <a href="https://bestimage.ai/"><img src="assets/bestimage-ai-logo.svg" width="72" height="72" alt="bestimage.ai 标志"></a>
</p>

# Awesome FLUX 3 提示词库

<p align="center">
  <img src="assets/flux-3-prompts-hero.png" alt="灯塔守望者在暗色港湾上方放置琥珀色灯笼" width="100%">
</p>

84条完整视频提示词，涵盖故事、产品短片、动画、教育及参考素材控制场景。由 [bestimage.ai](https://bestimage.ai/) 团队整理与维护。

[English](README.md) · 简体中文 · [日本語](README_ja-JP.md) · [Español](README_es-ES.md) · [语言覆盖范围](i18n/README.md)

[![官网](https://img.shields.io/badge/Website-bestimage.ai-4C52FE)](https://bestimage.ai/)
[![FLUX 3 API](https://img.shields.io/badge/FLUX_3-API-111827)](https://bestimage.ai/models/black-forest-labs/flux-3-text-to-video/)
[![GPT Image 2 API](https://img.shields.io/badge/GPT_Image_2-API-111827)](https://bestimage.ai/models/openai/gpt-image-2/)

## 从一个能够明确指导的场景开始

1. 浏览[84条提示词总索引](prompts/README.md)或[使用场景矩阵](docs/use-case-matrix.md)。
2. 选择文字、一张已确认的首帧图像、两张已确认的首尾帧图像，或一段源视频。
3. 复制完整的提示词代码块。调整指定变量，同时保持物体数量和连续性。
4. 在延续场景之前，按照[提示词指南](docs/prompting-guide.md)检查结果。

这些创作说明可作为设计场景的起点。要求特定运镜、精确台词或首尾帧匹配，并不代表模型必定能输出相应结果。

## 使用 bestimage.ai 创作

bestimage.ai 团队维护这个独立提示词库，整理实用的图生视频前期准备与 API 工作流。本项目不是 Black Forest Labs 官方仓库。

| 起始素材 | bestimage.ai 入口 | 用途 |
| --- | --- | --- |
| 文字场景描述 | [FLUX 3 文生视频](https://bestimage.ai/models/black-forest-labs/flux-3-text-to-video/) | 探索新场景、对白或视觉讲解 |
| 一张已确认的图像 | [FLUX 3 图生视频](https://bestimage.ai/models/black-forest-labs/flux-3-image-to-video/) | 让提供的首帧构图动起来 |
| 开场与结尾图像 | [FLUX 3 首尾帧生视频](https://bestimage.ai/models/black-forest-labs/flux-3-start-end-to-video/) | 要求两帧之间形成受控过渡 |
| 已有视频片段 | [FLUX 3 视频续写](https://bestimage.ai/models/black-forest-labs/flux-3-video-extend/) | 延续源视频的动作、场景状态与环境氛围 |
| 分镜或参考帧创作说明 | [GPT Image 2 API](https://bestimage.ai/models/openai/gpt-image-2/) | 在独立的视频制作步骤之前，准备或修改**静态图像** |

GPT Image 2 是独立的图像工作流，不是 FLUX 3 视频接口。将图像用作视频参考之前，应确认图像内容及其使用权。生成一张可用的参考帧，并不能验证后续视频的质量。

[12条面向 API 的创作说明](prompts/bestimage-api-workflows.md)与文档列出的模型 ID 和媒体字段相对应。[集成指南](docs/bestimage-ai-flux-3-api.md)使用 **bestimage.ai 的 API 主机 `https://api.flaq.ai`**，请使用在 bestimage.ai 账户中获取的 API 密钥。

## 提示词库

| 分类 | 提示词数量 | 适用场景 |
| --- | ---: | --- |
| [电影叙事](prompts/cinematic-storytelling.md) | 6 | 小故事、画面空间关系与剪辑节奏 |
| [广告与用户生成内容](prompts/advertising-ugc.md) | 6 | 产品交互、创作者内容与服务片段 |
| [纪录片与自然](prompts/documentary-nature.md) | 6 | 合成纪实风格场景与耐心观察 |
| [动画与设计](prompts/animation-design.md) | 6 | 纸艺、毛毡、黏土、文字设计与原创角色动作 |
| [多语言音频](prompts/multilingual-audio.md) | 6 | 精确对白、轮流发言与原创人声表演 |
| [参考素材工作流](prompts/reference-workflows.md) | 6 | 首帧身份特征、首尾帧与连续性 |
| [电商与产品](prompts/ecommerce-product.md) | 6 | 零件数量、包装、材质与产品几何形态 |
| [旅行与酒店服务](prompts/travel-hospitality.md) | 6 | 尊重他人的交流、场所取景与服务 |
| [运动与健康](prompts/sports-wellness.md) | 6 | 低风险运动与包容性的社区活动片段 |
| [教育与科学](prompts/education-science.md) | 6 | 可检验的小型教学内容与清晰指令 |
| [建筑与交通](prompts/architecture-mobility.md) | 6 | 可见空间、路线与物流 |
| [社交与实验](prompts/social-experimental.md) | 6 | 冷面幽默、创作者对白、游戏概念与合成底片 |
| [bestimage.ai API 工作流](prompts/bestimage-api-workflows.md) | 12 | 文档列出的四种视频模式，每种各有三条创作说明 |

每个条目都包含用途、模式、时间安排、可见动作、声音方案、固定条件、禁止项和可调整范围。参考素材必须有明确的用途；不要让风格参考图改变已有产品或人物的特征。

## 精选提示词

封面场景: [C01 — 灯笼接力](prompts/cinematic-storytelling.md#c01)：一个由场景内灯光发出的微小信号，带出虚构的海岸世界。

封面和五张配图是原创静态概念图，并非 FLUX 3 视频输出。完整提示词与来源见[素材说明](assets/IMAGE_PROMPTS.md)。

### [A01 — 穿过亚麻的光](prompts/advertising-ugc.md#a01)

用一次开关操作改变照明，同时保持灯具的几何形态。

<p align="center">
  <img src="assets/featured/light-through-linen.png" alt="褶皱亚麻灯罩、陶土灯座和一个线控开关组成的台灯" width="58%">
</p>

### [N01 — 纽扣天文台](prompts/animation-design.md#n01)

以纸板望远镜和毛毡天文学家，讲述富有触感的微缩故事。

<p align="center">
  <img src="assets/featured/button-observatory.png" alt="毛毡天文学家在纸板望远镜旁观察一颗白色四孔纽扣" width="100%">
</p>

### [E01 — 两块隔板，一个位置](prompts/ecommerce-product.md#e01)

组装说明明确区分三个产品零件与作为道具的笔记本。

<p align="center">
  <img src="assets/featured/two-dividers.png" alt="两块竖直隔板支撑一本合上的蓝色笔记本的木质收纳架" width="100%">
</p>

### [L01 — 移动卡片，不移动光源](prompts/education-science.md#l01)

固定光源与屏幕，完成一个清晰的影子演示。

<p align="center">
  <img src="assets/featured/shadow-card.png" alt="灯光经过不透明方形卡片，在白色屏幕上形成放大的影子" width="100%">
</p>

### [X01 — 一句有用的话](prompts/social-experimental.md#x01)

精确对白、五秒停顿，不添加额外笑点。

<p align="center">
  <img src="assets/featured/one-useful-sentence.png" alt="身穿灰色针织衫的主持人坐在桌前，面前只有一个麦克风和一本合上的笔记本" width="58%">
</p>

## 模型能力与 API 支持范围

Black Forest Labs 将 FLUX 3 描述为多模态模型，并在文档中介绍了支持文字、图像与视频参考、关键帧、续写和原生音频的视频生成能力。其视频、图像、动作及开放权重组件具有不同的开放状态。依赖某项访问权限或能力之前，请查看[官方模型页面](https://bfl.ai/models/flux-3)与[发布介绍](https://bfl.ai/blog/flux-3)。

模型层面的整体介绍，并不意味着每个服务提供方都开放了全部输入方式。本提示词库的 bestimage.ai 工作流包仅使用文档列出的四种视频模式。尤其需要注意，单个 `image_url` 首帧字段并不等于通用的多参考素材数组。

## 语言覆盖范围

- 四份项目介绍：英语、简体中文、日语和西班牙语。
- 十一个非英语场景文件：中文、日语、西班牙语、法语、德语、韩语、巴西葡萄牙语、意大利语、阿拉伯语、俄语和印度尼西亚语。
- 每个场景文件都翻译相同的三个标准场景：X01、E01 和 L01。这33条译文**不是额外的33条原创提示词**。
- 完整的84条提示词及制作指南以英语维护。本地化文件不是全库完整译文。

具体文件和覆盖范围请查看[语言目录](i18n/README.md)。

## 发布结果前先检查

使用已获授权的参考图，以及已获本人同意使用的身份特征和声音。检查动作、人体结构、物体数量、对白、文字和首尾帧连续性。合成产品演示不能证明产品性能；虚构场所的场景也不能证明现实中确有相应服务。业务关键信息和已核实的测量数据应在后期制作中添加。

## 参与贡献

欢迎分享实用提示词、案例和译文，请先阅读[贡献指南](CONTRIBUTING.md)。

## 关于 bestimage.ai

本提示词库由 [bestimage.ai](https://bestimage.ai/) 团队整理与维护，将实用创作流程与图像、视频模型 API 连接起来。

## 加入 bestimage.ai 联盟推广计划

制作教程、分享提示词或发布 API 集成案例？加入 [bestimage.ai 联盟推广计划](https://bestimage.ai/affiliate-program/)，向你的受众推荐 bestimage.ai，并获得推荐佣金。

- 受推荐用户的首笔有效付费订单，佣金为 **20%**。
- 该用户**注册后 60 天内**的后续有效付费订单，佣金为 **10%**。

订单资格与结算以[现行联盟协议](https://bestimage.ai/affiliate-agreement/)为准。

## 许可证

[MIT](LICENSE).
