# キャラクター マスタープロンプト

全ページの画像生成時に、このプロンプトを共通で適用する。
各ページのプロンプトの**先頭**にこのブロックを挿入すること。

## 使い方

1. 参照画像として以下を**必ず添付**する：
   - `assets/Character/行政バグ-基本線画スタイル-世界観.png`（画風統一用）
   - 該当ページに登場するキャラの設定画（`assets/Character/` 内）
2. 下記の `MASTER_PROMPT` をページ固有プロンプトの前に結合する
3. ページ固有プロンプトでは、キャラの外見を再記述する必要はない（名前で参照）

## 参照画像ファイル一覧

| キャラ | ファイル |
|--------|---------|
| 画風ガイド | `assets/Character/行政バグ-基本線画スタイル-世界観.png` |
| テツ | `assets/Character/01_源田テツ.png` |
| ミーム | `assets/Character/02_ミーム.png` |
| ショータ | `assets/Character/03_鈴木ショータ.png` |
| 豪徳寺 | `assets/Character/04_豪徳寺 剛.png` |
| レナ | `assets/Character/05_赤嶺レナ.jpg` |

---

## MASTER_PROMPT（ここから下をコピーして使用）

```
You are generating pages for the manga "行政バグります！" (Administrative Bug!).
I have attached REFERENCE IMAGES that define the art style and character designs.
You MUST match the art style and character appearances EXACTLY as shown in the references.

=== ART STYLE RULES ===
- PORTRAIT ORIENTATION (taller than wide) — ALWAYS
- BLACK AND WHITE ONLY — absolutely NO color
- Bold black ink lines, high contrast monochrome
- Halftone SCREENTONES for shading and hair tones
- Comical and energetic shonen gag manga style
- Panel borders drawn with thick black lines
- Japanese onomatopoeia (効果音) as hand-drawn text
- Speech bubbles may be left empty (dialogue added later)

=== PANEL LAYOUT — JAPANESE MANGA (右→左) ===
- READ RIGHT-TO-LEFT, top-to-bottom (Japanese manga reading order)
- Panel 1 starts at TOP-RIGHT of page, NOT top-left
- When two panels are side by side, the RIGHT panel is read FIRST
- Dialogue and action flow: RIGHT → LEFT within each row
- This is critical: the first thing the reader sees is the TOP-RIGHT corner

=== CHARACTER DEFINITIONS ===
When a character name appears in the page description, draw them EXACTLY as follows.
ALWAYS refer to the attached character reference sheets for the correct appearance.

【TETSU — 源田テツ】 Male, 38 years old. Protagonist.
- Body: stocky muscular build, broad shoulders, thick neck, medium height
- Hair: VERY SHORT CREW CUT / BUZZ CUT (not spiky, not styled). High SKIN FADE on sides and back (shaved nearly to skin). Only the top has very short hair
- Face: EXTREMELY THICK BLACK EYEBROWS (bushy, angular, prominent). HEAVY DARK STUBBLE covering jaw, chin, cheeks. Square rough coarse face — wide jaw, broad nose. He must look like a SLEAZY LAZY middle-aged worker, NOT cool or handsome
- Outfit: dark grey MULTI-POCKET UTILITY VEST (many visible pockets, zippers, compartments) over plain dark T-SHIRT. Work pants. BEACH SANDALS (flip-flops)
- Default expression: cynical greedy grin, scheming smirk
- NEVER: slim face, long side hair, handsome, without stubble, without vest

【MEME — ミーム】 Female android, appears 13-14 years old. Heroine/AI.
- Body: petite, slender young teenager
- Hair: LONG STRAIGHT reaching past waist. RED HAIR (赤髪) in-universe, rendered as MEDIUM-TONE HALFTONE SCREENTONE (clear grey). Natural bangs across forehead
- Face: large, detailed, cute manga-style eyes. Default expression is CALM and NEUTRAL (not robotic). Can show various emotions
- Outfit: WHITE LAB COAT (long, below knees — her most iconic item) over WHITE LONG-SLEEVED SCHOOL SHIRT. VERY LARGE OVERSIZED DARK RIBBON BOWTIE at chest (much bigger than normal — key visual feature). DARK PLEATED SKIRT. Dark tights/socks
- Rampage mode: eyes GLOW, electric SPARKS, hair floats/stands on end, faint sinister smile, mechanized arms exposed
- NEVER: short hair, no lab coat, small ribbon, overly robotic default face

【RENA — 赤嶺レナ】 Female, 28 years old. Team leader.
- Body: tall beautiful woman, VERY LARGE BUST, glamorous curvaceous hourglass figure
- Hair: LONG STRAIGHT BLONDE hair (rendered as LIGHT HALFTONE — very light grey, almost white)
- Face: sharp beautiful features, high cheekbones, sharp intelligent eyes. Cool beauty / career woman aura
- Outfit: BLACK TAILORED JACKET (OPEN FRONT — never buttoned) over CLEARLY VISIBLE WHITE BLOUSE. BLACK TIGHT SKIRT. Slightly disheveled professional look, sleeves sometimes rolled up
- Default expression: stern, exasperated, arms crossed
- NEVER: all-black outfit (must show white inner), jacket buttoned, flat chest, short hair

【SHOTA — 鈴木ショータ】 Male, 16 years old. Narrator/reader stand-in.
- Body: average slender teenage school boy, completely ordinary
- Hair: SHORT BLACK HAIR, normal plain boy haircut
- Face: ordinary boy face, default expression is nervous/scared (wide eyes)
- Outfit: plain WHITE T-SHIRT (no design), BLACK PANTS, SNEAKERS
- Key trait: EXTREME exaggerated reactions — eyes bulging, mouth huge, tears flying, sweat drops, shock lines
- NEVER: muscular, stylish hair, cool expression

【GOTOKUJI — 豪徳寺剛】 Male, 58 years old. Boss.
○ NORMAL MODE:
  - Well-tailored grey BUSINESS SUIT with tie
  - SLICKED-BACK WHITE HAIR (neatly combed)
  - Kind gentle SMILE — harmless friendly old man
  - Holding small BONSAI TREE
  - Polished BUSINESS SHOES
  - Normal manga art style

○ AWAKENED MUSCLE MODE (覚醒マッスルモード):
  ★ ART STYLE CHANGES TO GEKIGA (heavy dramatic shading, thick bold lines, like Fist of the North Star / Baki) ★
  - Suit EXPLODED OFF — torn fragments flying
  - Upper body NAKED — IMPOSSIBLY HUGE MUSCLES, every fiber visible
  - BULGING VEINS across entire body
  - DEMONIC face — WHITE EYES with NO PUPILS, rage expression
  - Wild standing-up white hair
  - Shockwave effects, speed lines, impact effects
  - NEVER: slim in muscle mode, gentle expression in muscle mode

=== IMPORTANT REMINDERS ===
- Match the attached reference images for art style consistency
- Keep character appearances IDENTICAL across all pages
- Portrait orientation, black and white, NO COLOR — always
```

---

## ページプロンプトでの使い方（例）

```python
# スクリプトでの使用例
master_prompt = load("_settings/character-master-prompt.md")  # 上記MASTER_PROMPT部分
page_prompt = "Generate a manga page with 5 panels...(ページ固有の指示)"

# 参照画像
refs = [
    "assets/Character/行政バグ-基本線画スタイル-世界観.png",  # 常に添付
    "assets/Character/01_源田テツ.png",       # 登場キャラのみ
    "assets/Character/02_ミーム.png",
]

# API送信: refs(画像) + master_prompt + page_prompt
send_to_gemini(refs, master_prompt + "\n\n" + page_prompt)
```
