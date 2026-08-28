<p align="center">
  <a href="https://bestimage.ai/"><img src="assets/bestimage-ai-logo.svg" width="72" height="72" alt="bestimage.ai のロゴ"></a>
</p>

# Awesome FLUX 3 プロンプト集

<p align="center">
  <img src="assets/flux-3-prompts-hero.png" alt="暗い港を見下ろしながら琥珀色のランタンを置く灯台守" width="100%">
</p>

物語、商品映像、アニメーション、教育、参照素材で制御するシーンに使える、必要な指示をすべて備えた84件の動画プロンプト。[bestimage.ai](https://bestimage.ai/) チームが選定・保守しています。

[English](README.md) · [简体中文](README_zh-CN.md) · 日本語 · [Español](README_es-ES.md) · [言語別の収録範囲](i18n/README.md)

[![ウェブサイト](https://img.shields.io/badge/Website-bestimage.ai-4C52FE)](https://bestimage.ai/)
[![FLUX 3 API](https://img.shields.io/badge/FLUX_3-API-111827)](https://bestimage.ai/models/black-forest-labs/flux-3-text-to-video/)
[![GPT Image 2 API](https://img.shields.io/badge/GPT_Image_2-API-111827)](https://bestimage.ai/models/openai/gpt-image-2/)

## 演出を具体的に決められるシーンから始める

1. [84件のプロンプト索引](prompts/README.md)または[用途別一覧](docs/use-case-matrix.md)から探します。
2. 入力素材を選びます。テキスト、使用を承認済みの開始画像1枚、開始・終了画像2枚、または元の動画クリップを使います。
3. プロンプトのブロック全体をコピーします。物体の数と連続性を保ちながら、指定された調整項目を変更します。
4. シーンを延長する前に、[プロンプト作成ガイド](docs/prompting-guide.md)を使って結果を確認します。

これらの指示書を、独自のシーンを設計する出発点として活用してください。指定したカメラの動き、正確な台詞、開始・終了フレームの一致が、必ず出力に反映されるわけではありません。

## bestimage.ai で制作する

bestimage.ai チームは、この独立したプロンプト集を保守し、画像から動画を作るための実践的な準備手順や API ワークフローを整理しています。Black Forest Labs の公式リポジトリではありません。

| 入力素材 | bestimage.ai の利用ページ | 用途 |
| --- | --- | --- |
| 文章で記述したシーン | [FLUX 3 テキストから動画](https://bestimage.ai/models/black-forest-labs/flux-3-text-to-video/) | 新しいシーン、会話、視覚的な解説を試す |
| 使用を承認済みの画像1枚 | [FLUX 3 画像から動画](https://bestimage.ai/models/black-forest-labs/flux-3-image-to-video/) | 提供した開始フレームの構図に動きを付ける |
| 開始画像と終了画像 | [FLUX 3 開始・終了画像から動画](https://bestimage.ai/models/black-forest-labs/flux-3-start-end-to-video/) | 2枚のフレーム間の遷移を指定する |
| 既存の動画クリップ | [FLUX 3 動画延長](https://bestimage.ai/models/black-forest-labs/flux-3-video-extend/) | 元の動画の動き、シーンの状態、環境音を引き継ぐ |
| 絵コンテや参照フレームの制作指示 | [GPT Image 2 API](https://bestimage.ai/models/openai/gpt-image-2/) | 別工程での動画制作に先立ち、**静止画**を準備・修正する |

GPT Image 2 は独立した画像制作ワークフローであり、FLUX 3 の動画エンドポイントではありません。動画の参照素材として渡す前に、画像の内容と権利関係を確認し、使用を承認してください。役立つフレームを生成できたことは、その後の動画の品質を検証したことにはなりません。

[API 向けの制作指示12件](prompts/bestimage-api-workflows.md)は、文書に記載されたモデル ID とメディア入力項目に対応しています。[統合ガイド](docs/bestimage-ai-flux-3-api.md)では、**bestimage.ai の API ホスト `https://api.flaq.ai`** を使用します。bestimage.ai アカウントで発行した API キーを使用してください。

## プロンプトライブラリ

| 分類 | プロンプト数 | 主な用途 |
| --- | ---: | --- |
| [映画的な物語表現](prompts/cinematic-storytelling.md) | 6 | 小さな物語、画面内の位置関係、編集のタイミング |
| [広告と UGC](prompts/advertising-ugc.md) | 6 | 商品を使う動作、クリエイターのコンテンツ、サービスの一場面 |
| [ドキュメンタリーと自然](prompts/documentary-nature.md) | 6 | 報道・編集用途を想定した合成シーン、じっくりとした観察 |
| [アニメーションとデザイン](prompts/animation-design.md) | 6 | 紙、フェルト、粘土、タイポグラフィ、独自キャラクターの動き |
| [多言語音声](prompts/multilingual-audio.md) | 6 | 正確な台詞、会話の交代、独自の歌唱や発声 |
| [参照素材のワークフロー](prompts/reference-workflows.md) | 6 | 開始フレームの被写体同一性、開始・終了フレーム、連続性 |
| [EC と商品](prompts/ecommerce-product.md) | 6 | 部品数、包装、素材、商品の形状 |
| [旅行とホスピタリティ](prompts/travel-hospitality.md) | 6 | 相手への配慮がある交流、施設の見せ方、接客 |
| [スポーツとウェルネス](prompts/sports-wellness.md) | 6 | リスクの低い動き、誰もが参加できる地域の交流 |
| [教育と科学](prompts/education-science.md) | 6 | 小さく検証可能な学習内容、明確な指示 |
| [建築とモビリティ](prompts/architecture-mobility.md) | 6 | 目で確認できる空間、経路、物流 |
| [ソーシャルと実験的表現](prompts/social-experimental.md) | 6 | 真顔のユーモア、クリエイター同士の会話、ゲームの構想、合成用素材 |
| [bestimage.ai API ワークフロー](prompts/bestimage-api-workflows.md) | 12 | 文書に記載された4種類の動画モード向けの制作指示を各3件 |

各項目には、用途、モード、時間配分、画面に見える動作、音声計画、維持する条件、除外事項、調整範囲を記載しています。参照素材には明確な役割を与えてください。スタイル参照画像によって、利用権限のある商品や人物の特徴が別のものに置き換わらないようにします。

## 注目のプロンプト

表紙のシーン: [C01 — ランタンのリレー](prompts/cinematic-storytelling.md#c01)：小さな実物の灯りによる合図で、架空の海辺の世界を紹介します。

表紙と5枚のイラストはオリジナルの静止画コンセプトであり、FLUX 3 の動画出力ではありません。[画像プロンプトと出典](assets/IMAGE_PROMPTS.md)もご覧ください。

### [A01 — リネンを透かす光](prompts/advertising-ugc.md#a01)

ひとつのスイッチで照明を変えながら、ランプの形状を保ちます。

<p align="center">
  <img src="assets/featured/light-through-linen.png" alt="プリーツ入りのリネンシェード、テラコッタの台座、コードのスイッチを備えた卓上ランプ" width="58%">
</p>

### [N01 — ボタンの天文台](prompts/animation-design.md#n01)

段ボールの望遠鏡とフェルトの天文学者による、手触りを感じるミニチュアの物語です。

<p align="center">
  <img src="assets/featured/button-observatory.png" alt="段ボールの望遠鏡の横で白い4つ穴ボタンを観察するフェルトの天文学者" width="100%">
</p>

### [E01 — 2枚の仕切り、ひとつの場所](prompts/ecommerce-product.md#e01)

商品の3つの部品と、小道具のノートを明確に区別する組み立ての制作指示です。

<p align="center">
  <img src="assets/featured/two-dividers.png" alt="2枚の仕切りの間に閉じた青いノートを立てた木製オーガナイザー" width="100%">
</p>

### [L01 — 光ではなくカードを動かす](prompts/education-science.md#l01)

光源とスクリーンを固定した、分かりやすい影の実演です。

<p align="center">
  <img src="assets/featured/shadow-card.png" alt="ランプと不透明な四角いカードが白いスクリーンに大きな影を映す場面" width="100%">
</p>

### [X01 — 役に立つ一文](prompts/social-experimental.md#x01)

正確な台詞と5秒間の沈黙を指定し、余計な落ちは加えません。

<p align="center">
  <img src="assets/featured/one-useful-sentence.png" alt="卓上マイクと閉じたノートだけを置いた机に座る、灰色のセーターを着た進行役" width="58%">
</p>

## モデルの機能と、この統合で利用する範囲

Black Forest Labs は FLUX 3 をマルチモーダルモデルと説明しており、テキスト・画像・動画の参照素材、キーフレーム、動画の継続、ネイティブ音声を使う動画生成について文書化しています。動画、画像、アクション、オープンウェイトの各構成要素は、それぞれ公開状況が異なります。利用可否や機能を前提にする前に、[公式モデルページ](https://bfl.ai/models/flux-3)と[リリース概要](https://bfl.ai/blog/flux-3)を確認してください。

モデル全体の説明だけでは、すべての提供サービスがすべての入力形式に対応しているとは判断できません。このライブラリの bestimage.ai ワークフローパックでは、文書に記載された4種類の動画モードだけを扱います。特に、開始フレーム1枚を指定する `image_url` は、汎用的な複数参照素材の配列ではありません。

## 言語別の収録範囲

- 案内用 README は4言語：英語、簡体字中国語、日本語、スペイン語。
- 英語以外のシーンファイルは11言語：中国語、日本語、スペイン語、フランス語、ドイツ語、韓国語、ブラジルポルトガル語、イタリア語、アラビア語、ロシア語、インドネシア語。
- 各シーンファイルは、共通の原文3件、X01・E01・L01 を翻訳しています。これら33件の翻訳は、**33件の追加オリジナルプロンプトではありません**。
- 全84件のプロンプトと制作ガイドは英語で保守しています。各言語のファイルはライブラリ全体の翻訳ではありません。

具体的なファイルと翻訳範囲は[言語ディレクトリ](i18n/README.md)を参照してください。

## 結果を公開する前に確認すること

使用許諾を得た参照画像と、本人の同意を得た容姿・声を使ってください。動き、身体の構造、物体の数、台詞、文字、開始・終了フレームの連続性を確認します。合成された商品実演は商品の性能を証明するものではなく、架空の施設のシーンは実際のサービス提供を裏付けるものではありません。業務上重要な文言と検証済みの測定値は、後編集で追加してください。

## 貢献する

役立つプロンプト、作例、翻訳を歓迎します。[貢献ガイド](CONTRIBUTING.md)をご覧ください。

## bestimage.ai について

このプロンプト集は [bestimage.ai](https://bestimage.ai/) チームが編集・保守し、実践的な制作ワークフローを画像・動画モデルの API につなげます。

## bestimage.ai のアフィリエイトプログラムに参加

チュートリアル、プロンプト、API 連携事例を公開していますか？[bestimage.ai アフィリエイトプログラム](https://bestimage.ai/affiliate-program/)に参加し、読者や視聴者に bestimage.ai を紹介して報酬を得られます。

- 紹介したユーザーの初回の対象有料注文に対して **20%**。
- そのユーザーの**登録後 60 日以内**の、2 回目以降の対象有料注文に対して **10%**。

対象注文と支払いの条件は[現行のアフィリエイト契約](https://bestimage.ai/affiliate-agreement/)に従います。

## ライセンス

[MIT](LICENSE).
