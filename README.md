# UOS『AI Lead-Off』セミナー資料

Claude Code の活用方法を伝える社外向けセミナー「AI Lead-Off」のアジェンダ・題材・デザイン資料をまとめたリポジトリです。各回とも1時間構成で、講義とデモ（第2回はハンズオン中心）で進行します。

## セミナー構成

### 第1回：業務系編 — Claudeで日々の業務を変えよう

Claude Code を触ったことがない、または触り始めたばかりの人を対象に、Claude で何ができるかのインパクトを伝える回です。全体像の説明から、ライティング編（`/rewrite-ai-tone`）、デザイン編（ClaudeDesign → `/create-design-md` → モック生成 → `/create-slides-html`）、業務自動化事例まで、デモ中心で構成しています。

詳細は [docs/agenda_first_summrary.md](docs/agenda_first_summrary.md) を参照してください。

### 第2回：コーディング編 — Claude Codeで開発ワークフローを回す

架空アプリ「Mandalart App」の LP（ランディングページ）を題材に、ClaudeDesign での LP 生成から Claude Code への取り込み、README更新、コミット、ブランチ作成、顧客指摘対応、PR作成、セルフレビューまで、GitHub上の開発フローをハンズオンで一気通貫に体験する回です。

詳細は [docs/agenda_second_summrary.md](docs/agenda_second_summrary.md) を参照してください。

## リポジトリ構成

```
CLAUDE.md                      Claude Code向けの動作設定（言語・Git操作制限・環境変数ファイル制限等）
docs/
  agenda_first_summrary.md     第1回セミナーのアジェンダ
  agenda_second_summrary.md    第2回セミナーのアジェンダ
  slides/first-seminar/        第1回で使用するスライド（index.html）
design/
  アプリ設計.md                  Mandalart App の設計書（初版）。アプリの機能・課題・LPに必要な要素を整理
  アプリ設計2_顧客指摘.md         初版に対する顧客指摘と、それを反映するためのLP修正指示（差分）
  DESIGN.md                    Mandalart App LP のデザイン指定（配色・タイポグラフィ・レイアウト等）
  Mandalart LP.dc.html         ClaudeDesign で生成した Mandalart App LP の実体
```

## 題材アプリ：Mandalart App

個人の目標（マンダラート）を1on1・タスク・経歴・分析とひと続きにし、「目標の立てっぱなし・1on1のやりっぱなし」をなくす組織成長プラットフォームという設定の架空アプリです。第2回セミナーでは、このアプリのLPを実際の開発フローに沿って作成・修正します。

- 初版の仕様は [design/アプリ設計.md](design/アプリ設計.md)、見た目の指定は [design/DESIGN.md](design/DESIGN.md) にまとまっています。
- 顧客デモ後の指摘に基づく仕様変更（機能モジュールの削減、マンダラートの100セル化・改称、Slack連携の追加）は [design/アプリ設計2_顧客指摘.md](design/アプリ設計2_顧客指摘.md) にまとめられており、第2回セミナーのハンズオンでこの指摘をLPに反映します。

## 利用しているClaude Codeスキル

`.claude/skills/` 配下に、セミナー内で使用するカスタムスキルを配置しています。

| スキル | 用途 |
| ---- | ---- |
| `rewrite-ai-tone` | AIが書いた文章を、人が書いたような自然な日本語にリライトする |
| `create-design-md` | URLやPowerPointファイルからデザイントークンを抽出し DESIGN.md を生成する |
| `create-slides-html` | reveal.js + Tailwind CSS で人が作ったように見えるHTMLスライドを作成する |
| `update-readme` | 実装内容に合わせて README.md を更新する |
| `commit-changes` | 未コミットの変更をまとめてコミットメッセージを生成する |
| `create-pr` | ブランチ名とコミット内容からタイトル・説明を自動生成してPRを作成する |
| `review-and-fix` | PRをレビューし、指摘を重要度順に1件ずつ確認・修正する |
