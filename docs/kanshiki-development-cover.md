# AI鑑識学をつくる：表紙制作記録

- 制作日：2026-10-23
- 用途：Zenn Book の表紙
- 生成：組み込み画像生成ツール（CLI/APIフォールバック未使用）
- 画像：`books/kanshiki-development/cover.png`
- 寸法：1060 × 1484 px（5:7）
- SHA-256：`525db586028c427222f83c75e48bb40eeb1a492a564812b404584549faa27af6`
- 意匠：濃紺、アイボリーの原稿、朱色の校正線。文章間の関係を追う観察と開発の試行錯誤を表す。
- 画像内の原稿は装飾用の抽象表現であり、実験証拠や実際の原稿ではない。

## 生成プロンプト

```text
Use case: ads-marketing.
Asset type: final Japanese nonfiction ebook front cover for a Zenn Book, flat full-bleed artwork, portrait aspect ratio exactly 5:7, ideally 1000×1400 pixels or 1500×2100. Single cover, no book mockup and no surrounding background.
Book subject: a readable development journal of a Japanese text-observation tool, from trial and error to v5; evidence, relationships between passages, useful withholding of judgement, and revision. It is about careful reading and engineering, not crime scenes or magically detecting who wrote something.
Design: premium Japanese technical paperback, editorial Swiss-grid typography with a tactile research-notebook sensibility. Deep midnight navy background, warm ivory typography and paper, a restrained vermilion-red accent. Strong confident negative space. Top half devoted to VERY LARGE impeccably legible Japanese title; lower half an elegant abstract close-up of two ivory manuscript strips overlapping slightly, charcoal lines suggesting prose (NOT random fake readable words), a few red proofreader underlines and thin relation lines connecting two highlighted fragments, one small vermilion square annotation marker. Thin precise geometric construction lines and subtle printed-paper grain. The graphic must feel intentional, literary and analytical, not a busy futuristic dashboard.
Text: Render these exact strings accurately, and no other words:
Main title, largest: 「AI鑑識学を」「つくる」 (two lines; do not draw the quote brackets).
Subtitle, smaller but readable: 「開発の試行錯誤と」「v5への変遷」 (two lines; do not draw the quote brackets).
Author at bottom: 「黒い黒パグ」 (do not draw the quote brackets).
Keep all text at least 8% of canvas width away from edges. Main title should remain legible at thumbnail size. Use modern Japanese bold sans-serif for main title with excellent kerning, lighter restrained type for subtitle and author. Dominant title occupies upper 40%, illustration middle/lower 40%, author bottom 10%. Balanced asymmetry, refined commercial book-cover quality.
Avoid: robots, brains, fingerprints, binary rain, glowing circuits, neon cyberpunk, police badges, magnifying-glass clipart, people, animals, extraneous English slogans, meaningless dense text, logos, watermarks, 3D perspective, decorative fake certification stamps. Opaque background.
```
