# Page XX - Episode XXX「タイトル」

## シーン説明

（このページで何が起きているか、文章で簡潔に説明）

## パネル構成

| コマ | サイズ | 内容 |
|------|--------|------|
| 1 | 大 | （メインの見せゴマ） |
| 2 | 中 | |
| 3 | 中 | |
| 4 | 小 | |

## 画像生成プロンプト

### メインプロンプト

```
[共通スタイル], [キャラbase_prompt], [シーン固有の指定],
[構図・カメラアングル], [表情・ポーズ], [背景・エフェクト]
```

**組み立て例:**
```
shonen manga, gag manga, high contrast black and white, comic book style,
portrait orientation, 1480x2100px,
[ここにキャラのbase_promptを挿入],
[シーン: 例 "standing in messy office, pointing at computer screen"],
[構図: 例 "medium shot, slightly low angle"],
[エフェクト: 例 "speed lines, sweat drops, exclamation marks"]
```

### ネガティブプロンプト

```
photorealistic, 3D render, color image, sketch, messy lines,
landscape orientation, horizontal image,
blurred text, gibberish, english text, unreadable text,
low quality, blurry, missing details in background,
empty speech bubbles
[ここにキャラ固有のネガティブプロンプトを追加]
```

### 参照画像

- キャラ設定画: `_settings/characters/[キャラ名].png`
- スタイル参考: `_settings/characters/` 内の画像

## セリフ一覧（後から合成用）

| コマ | キャラ | セリフ | 吹き出しタイプ |
|------|--------|--------|----------------|
| 1 | | | 通常 / 叫び / ナレーション |
| 2 | | | |
| 3 | | | |
| 4 | | | |

## オノマトペ

| コマ | テキスト | サイズ | 配置 |
|------|----------|--------|------|
| | | | |

## 生成メモ

- 使用ツール: Gemini / nanobanana
- リテイク回数:
- 採用バージョン:
- 備考:
