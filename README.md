# 行政バグります！ ～稲城市役所・特務トレンド係～

週刊連載漫画の制作管理リポジトリ。

## エピソード一覧

| 話数 | フォルダ | タイトル |
|------|----------|----------|
| 第001話 | [ep001](episodes/ep001/) | ようこそ特務トレンド係へ |
| 第002話 | [ep002](episodes/ep002/) | SaaSは死んだ、窓口も死んだ |
| 第003話 | [ep003](episodes/ep003/) | 稲城市、バレンタインに全員にチョコを |
| 第004話 | [ep004](episodes/ep004/) | おばあちゃんのネコ、市が探します |

※ 全話の一覧は [episodes/README.md](episodes/README.md) を参照。

## フォルダ構成

```
行政バグります/
├── _settings/              # 作品全体の設定（不変）
│   ├── world.md            # 世界観・舞台・ルール
│   ├── style-guide.md      # 画風・フォーマット・プロンプト設定
│   └── characters/         # キャラクター別設定（md + 設定画）
│
├── _templates/             # エピソード制作テンプレート
│   ├── episode-template.md # 1話分の脚本雛形
│   └── page-prompt-template.md  # 1ページ分のプロンプト雛形
│
├── episodes/               # 各話のデータ（毎週増える）→ 一覧は episodes/README.md
│   ├── README.md           # エピソード一覧（話数・タイトル）
│   └── epXXX/
│       ├── script.md       # 脚本
│       ├── prompts/        # ページごとの画像生成プロンプト
│       ├── generated/      # 生成画像（未加工）
│       ├── finals/         # 最終ページ（セリフ入れ後）
│       └── status.md       # 進捗管理
│
└── assets/                 # 共通素材
    ├── cover.png           # 表紙
    └── backgrounds/        # 再利用可能な背景素材
```

## 週刊制作ワークフロー

| 曜日 | 作業内容 | 成果物 |
|------|----------|--------|
| 月 | プロット・脚本作成 | `script.md` のあらすじ・登場キャラ・ページ構成 |
| 火 | コマ割り・演出設計 | `script.md` のページ詳細を完成 |
| 水 | プロンプト作成 | `prompts/p01.md` 〜 `p20.md` |
| 木 | 画像生成 | `generated/` に出力（Gemini / nanobanana） |
| 金 | 修正・リテイク | 品質チェック → 再生成 |
| 土 | セリフ入れ・仕上げ | `finals/` に最終版保存 |
| 日 | 公開 → 次話プロット着手 | 公開 + 次回 `script.md` 開始 |

## 新しい話を始めるとき

1. `episodes/` に新しいフォルダを作成（例：`ep002/`）
2. `_templates/episode-template.md` を `ep002/script.md` にコピー
3. `prompts/`, `generated/`, `finals/` フォルダを作成
4. `_templates/page-prompt-template.md` を使ってプロンプトを作成
5. `status.md` で進捗を管理

```bash
# 新しいエピソードの作成コマンド例
mkdir -p episodes/ep002/{prompts,generated,finals}
cp _templates/episode-template.md episodes/ep002/script.md
cp episodes/ep001/status.md episodes/ep002/status.md
```

## 画像生成の流れ

1. `_settings/style-guide.md` から共通プロンプトを取得
2. `_settings/characters/[キャラ名].md` からキャラのbase_promptを取得
3. `script.md` のコマ指示からシーン固有のプロンプトを作成
4. 上記を結合して `prompts/pXX.md` に記録
5. Gemini / nanobanana で画像生成 → `generated/` に保存
6. リテイク後、セリフを合成して `finals/` に保存

## 仕様

- 1話あたり: 16〜20ページ
- 画像サイズ: 1480 x 2100 px（縦長）
- カラーモード: モノクロ（白黒 + スクリーントーン）
- 画像生成ツール: Gemini + nanobanana
