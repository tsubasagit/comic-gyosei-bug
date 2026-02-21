# スタイルガイド - 『行政バグります！』

## 画像フォーマット

| 項目 | 設定 |
|------|------|
| サイズ | 1480 x 2100 px（縦長厳守） |
| カラーモード | モノクロ（白黒 + スクリーントーン） |
| レイアウト | single_column |

## 画風指定（共通ベースプロンプト）

```
shonen manga, gag manga, high contrast black and white, comic book style,
monochrome, screentones, bold ink lines, portrait orientation
```

## ネガティブプロンプト（共通）

```
photorealistic, 3D render, color image, sketch, messy lines,
landscape orientation, horizontal image,
blurred text, gibberish, english text, unreadable text,
low quality, blurry, missing details in background,
empty speech bubbles
```

### キャラ固有ネガティブ

| キャラ | ネガティブプロンプト |
|--------|---------------------|
| テツ | handsome genda tetsu, slim genda tetsu, (tetsu with long side hair:1.5) |
| レナ | (rena all black clothes:1.5), (rena black inner top:1.5), (rena buttoned up jacket:1.3), (rena flat chest:1.5), (rena small breasts:1.5) |

## ビジュアルスタイル方針

- 力強い線画と高コントラストな白黒表現。網点トーンやベタ塗りを多用する
- キャラクターの顔立ち・体型・服装は設定画を厳密に再現する
- コミカルでエネルギッシュな雰囲気を重視し、リアクションは過剰に強調する
- 背景には集中線や効果線（speed lines, focus lines）を多用し、勢いを表現する

## セリフ・テキストのルール

- 吹き出し内には指定された**日本語のセリフ**を明瞭かつ正確に描画する
- 文字は**縦書き（vertical text）**を推奨
- フォント：太めのゴシック体やアンチック体風を意識
- セリフは誤字脱字なく、読みやすいサイズで配置
- オノマトペ（描き文字）は日本語で配置（例：「ドンッ」「ガーン」「シュオオオ」）

## Gemini / nanobanana 共通設定メモ

- 画像生成時は必ず `portrait orientation` を指定
- 各キャラの `base_prompt` に共通スタイルプロンプトを結合して使用
- loraタグ（loraGendaTetsu1.2 等）はキャラ固有プロンプトに含まれている
- 豪徳寺は通常モード / 覚醒モードで別プロンプトを使い分ける
- 参考スタイル画像: `_settings/characters/` 内の設定画を参照画像として利用

## コマ割りの基本方針

- 1ページあたり4〜6コマを基本とする
- アクションシーン / リアクションシーンでは見開き風の大ゴマを使用
- 豪徳寺の覚醒シーンは必ず大ゴマ or 全面使用
