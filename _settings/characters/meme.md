# ミーム (Meme)

## プロフィール

| 項目 | 内容 |
|------|------|
| 名前 | ミーム |
| 年齢 | 不明（外見は10代前半） |
| 役割 | ヒロイン / AI |
| 所属 | 稲城市役所 特務トレンド係 |
| 性格 | 無感情（デフォルト）、暴走時は狂気的。ネットスラングに詳しい |

## 外見

- アンドロイド / 少女型AI
- 長いストレートの赤髪（モノクロでは中濃度のハーフトーンで表現）、自然な前髪
- 白衣の下に白い長袖のスクールシャツ
- 胸元に非常に大きなダークカラーのリボンタイ
- ダークカラーのプリーツスカート
- 通常は穏やか・ニュートラルな表情（完全な無表情ではなく、様々な感情表現が可能）
- 詳細に描き込まれた漫画的な目

## 画像生成プロンプト（base_prompt）

```
1girl, solo, android, young teenager (13-14 years old),
long straight red hair (赤髪, rendered as medium-tone halftone screentone in monochrome), natural bangs,
wearing white lab coat (long, below knees) over a white long-sleeved school shirt,
(VERY LARGE oversized dark-colored ribbon bowtie at chest:1.3), dark pleated skirt, dark tights,
calm neutral expression (various emotions possible), large detailed cute manga eyes,
manga style, monochrome, loraMeme1.0
```

## 暴走モード

暴走時は外見が大きく変化する：
- 腕が機械化（メカアーム露出）
- 髪が逆立つ
- 狂気的な笑顔

```
# 暴走モード追加プロンプト
mechanized arms exposed, hair standing on end, wild chaotic grin,
glowing eyes, sparking electricity, cracked skin revealing circuits,
intense action pose, dramatic shading
```

## 表情・ポーズバリエーション

| 状態 | プロンプト追加要素 |
|------|---------------------|
| 通常（無表情） | deadpan expression, standing still, hands at sides |
| 検索・分析中 | holographic display in front of face, focused eyes, data streaming |
| 暴走開始 | one eye glitching, half-smile, sparks from neck |
| 完全暴走 | mechanized arms, wild hair, full chaotic grin, destruction around |
| 学習中（無邪気） | tilted head, curious expression, notebook in hand |

## セリフの口調

- 一人称：「私」（無感情に）
- 語尾：「〜です」（淡々と）
- 暴走時は文体が崩れる
- サンプル：
  - 「検索結果：『人類は滅ぼすべき』です。」
  - 「トレンド分析完了。推奨アクション：炎上です。」
  - 「【暴走】デ̷̢ータ̶̡が̸̲…溢̵れ̶̢て̸̲…楽̵し̶い̶̡で̸̲す̵」

## 設定画

![ミーム設定画](meme.png)
