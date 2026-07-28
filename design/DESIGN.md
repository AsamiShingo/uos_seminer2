# Design System — Mandalart App LP

> 実測元: 本LP（`docs/second-seminar/sample/`）の `index.html` / `style.css`

## Quick Color Reference
```
Primary        #5363B4
Primary Dark   #383874
Primary Bright #758BFD
Text (ink)     #141432
Text Sub       #626276
Text Muted     #9393A1
Pale Blue      #C0CAFF   Deep Blue #A3B1FE
Pale Red       #FEA5A5   Deep Red  #FD7C7C
Pale Yellow    #FFE88F   Deep Yellow #FFDE5C
Pale Mint      #A4E6C7   Deep Mint #7BDBAD
Pale Pink      #FFB0D6   Purple    #E8B5FB
Surface Grey   #F9F9F9 / #F2F2F2
Border         #E8E8EB (card) / #EBEBEB (input)
Pale Blue BG   #F1F3FF   Warm Yellow BG #FFFAE7
Background     #FFFFFF
```

## Typography
- 和文: 'Noto Sans JP', 'Hiragino Kaku Gothic ProN', sans-serif
- 英数字/ラベル/ロゴ: 'Manrope', sans-serif
- base: color #141432 / line-height 1.6 / letter-spacing 0.03em
- Hero title 2.5rem/700 (accent語 #5363B4) / Section title 1.75rem/700 (SP 1.375rem)
- Section label: Manrope 0.75rem/600, uppercase, letter-spacing .1em, #5363B4
- Card title 1.125rem/600 / body 1rem–0.875rem #626276 / caption 0.75rem #9393A1

## Radius
sm .25rem (tag) / base .5rem (button, FAQ, input) / xl 1.25rem (card, form, image) / 100px pill / 50% dot

## Shadow
- light `0 0 4px rgba(0,0,0,0.1)`
- brand `0 0 1.5rem rgba(56,56,116,0.1)` ← hover / 強調
- strong `0 0 12px rgba(0,0,0,0.25)`（予備）

## Layout
- container 1100px（料金/連絡先 960px、スクショ 900px、FAQ 720px、subtitle 640px）
- section padding 5rem 0（SP 3.5rem）
- grid: 機能 repeat(2,1fr) / お悩み・利用シーン・料金 repeat(3,1fr) / footer 1.5fr repeat(3,1fr)、gap 1.5–2rem
- breakpoints: 991px（Hero 1カラム・ハンバーガー）/ 767px（全1カラム）/ 479px（root 15px）

## Components
- Button base: inline-flex, gap .5rem, border 1px #141432, radius .5rem, 1rem/500, ls .04em
  - primary: #141432 地/白字, padding .875rem 2rem → hover 反転
  - outline: 白地/濃紺字 → hover 反転 / white: CTA帯用 / small: .625rem 1.25rem, .875rem
  - 矢印SVG .75rem、hover translateX(3px)
- Feature card: radius 1.25rem, shadow-light, 16/9 画像, padding 1.5rem, パステル丸タグ+タイトル+説明+ドットリスト、hover shadow-brand + 画像 scale(1.03)
- Usecase card: border-top 3px（淡青→淡黄→淡ミント）、hover translateY(-4px)、末尾 italic 引用
- Pricing card: padding 2.5rem 2rem 中央寄せ、featured は枠 #5363B4 + brand shadow + おすすめピル、✓ は #7BDBAD
- Section heading: ラベル → タイトル → サブタイトル（max-width 640px, margin-bottom 3rem）中央寄せ
- Header: fixed, 4rem, rgba(255,255,255,.96) + blur(8px), 下罫 #E8E8EB, スクロールで shadow-light
- Form: 白カード radius 1.25rem + shadow-light, 入力枠 #EBEBEB radius .5rem, focus 枠 #5363B4, 必須バッジ #FD7C7C

## Gradients（Hero と CTA のみ、135deg）
- Hero: `linear-gradient(135deg,#F1F3FF 0%,#fff 60%,#FFFAE7 100%)`, padding 8rem 0 5rem
- CTA: `linear-gradient(135deg,#383874 0%,#5363B4 50%,#758BFD 100%)`, 白文字

## Don'ts
純黒 #000 を本文に使わない / パステルを広面ベタ塗りにしない / シャープな角 / 黒い強い影 / #5363B4 を本文全般に広げない / グラデ多用 / 見出しに600未満
