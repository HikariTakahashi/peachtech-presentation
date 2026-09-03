---
marp: true
theme: peachtech-ui
size: 16:9
paginate: true
title: 5分で始めるMarp技術発表
author: PeachTech
footer: PeachTech Marp Template
---

<!-- _class: lead no-logo -->
<!-- _paginate: false -->

# AIが作れるプレゼンテーション

Markdownから、伝わるスライドへ

PeachTech / 2026

<!--
最初に、今日持ち帰ってほしいことを一言で伝えます。
-->

---

# 今日のゴール

> **内容に集中できる、再現可能な発表づくり**

- Markdownで構成と本文を書く
- VS Codeで結果をすぐ確認する
- PDF / PPTX / HTMLを同じ原稿から出力する

---

<!-- _class: section -->
<!-- _paginate: false -->

# Why Marp?

発表資料をコードと同じ流れで育てる

---

# よくある課題

| 課題                         | このテンプレートでの解決  |
| ---------------------------- | ------------------------- |
| 見た目の調整に時間がかかる   | テーマCSSに任せる         |
| ファイルの最新版が分からない | Gitで変更を管理する       |
| 出力形式ごとに作り直す       | 1つのMarkdownから生成する |

---

# 使い方は3ステップ

<div class="columns">
<div class="column">

## 1. 書く

`slides.md` を編集

## 2. 見る

VS Codeでプレビュー

</div>
<div class="column">

## 3. 出す

```bash
npm run export
```

PDF / PPTX / HTMLを生成

</div>
</div>

---

# 設計のポイント

- **1スライド1メッセージ**に絞る
- 見出しだけで話の流れが追えるようにする
- 詳細は発表者ノートへ分ける
- デモには失敗時の代替画面を用意する

---

<!-- _class: code-focus -->

# 最小のMarp Markdown

```md
---
marp: true
theme: peachtech-ui
size: 16:9
paginate: true
---

# 最初のスライド

結論を短く書きます。
```

---

# 画像は `assets/` に集約

<div class="image-center">

![PeachTechロゴ](assets/logo.png)

</div>

Markdownでは相対パスで参照します。

---

# まとめ

1. `slides.md` に内容を集約
2. `peachtech-ui` で見た目を統一
3. `npm run export` で3形式を生成

**まずはタイトルと結論を書き換えてみましょう。**

---

<!-- _class: lead no-logo -->
<!-- _paginate: false -->

# Q&A

ありがとうございました
