---
marp: true
theme: peachtech-ui
size: 16:9
paginate: true
footer: PeachTech Layout Samples
---

# 通常スライド

- 見出しは結論が分かる言葉にする
- 箇条書きは3〜5項目に絞る
- 強調する箇所を**1つ**決める

---

# 2カラム

<div class="columns">
<div class="column">

## 課題

- 手作業が多い
- 再現しにくい

</div>
<div class="column">

## 改善

- 自動化する
- 手順を共有する

</div>
</div>

---

# 画像中心

<div class="image-center">

![PeachTechロゴ](../assets/logo.png)

</div>

画像の意味を一文で補足します。

---

<!-- _class: code-focus -->

# コード中心

```ts
const message = 'Hello, PeachTech!';

function present(text: string): void {
  console.log(text);
}

present(message);
```

---

# 比較

<div class="columns compare">
<div class="column">

## Before

- 手順が人ごとに違う
- 出力にばらつきがある

</div>
<div class="column">

## After

- 手順をREADMEに集約
- テーマで見た目を統一

</div>
</div>

---

# 画像＋説明

<div class="media-split">
<div class="media-visual">

![PeachTechロゴ](../assets/logo.png)

</div>
<div class="media-copy">

## 見せたい画面

- 画像の意味を見出しで示す
- 説明は2〜3項目に絞る
- `reverse` を加えると左右を反転できる

</div>
</div>

---

# 数値・成果

<div class="stat-layout">
<div class="stat-primary">

<div class="stat-value">42%</div>
<div class="stat-label">作業時間を短縮</div>

</div>
<div class="stat-detail">

## 測定条件

- 同じ入力データで比較
- 5回の中央値
- 単位と比較対象を明記

</div>
</div>

---

# 処理フロー

<div class="process">
<div class="process-step">

## 入力

原稿を用意

</div>
<div class="process-step">

## 変換

Marpで解析

</div>
<div class="process-step">

## 確認

表示を検証

</div>
<div class="process-step">

## 出力

3形式を生成

</div>
</div>

---

# アーキテクチャ

<div class="architecture">
<div class="architecture-layer">
<div class="architecture-node">VS Code</div>
<div class="architecture-node">Cursor</div>
</div>
<div class="architecture-connector"></div>
<div class="architecture-layer">
<div class="architecture-node">Marp CLI</div>
</div>
<div class="architecture-connector"></div>
<div class="architecture-layer">
<div class="architecture-node">PDF</div>
<div class="architecture-node">PPTX</div>
<div class="architecture-node">HTML</div>
</div>
</div>

---

# コード比較

<div class="code-compare">
<div class="code-panel">

## Before

```js
const doubled = [];
for (const value of values) {
  doubled.push(value * 2);
}
```

</div>
<div class="code-panel">

## After

```js
const doubled = values.map(
  (value) => value * 2,
);
```

</div>
</div>

---

# デモ画面

<div class="demo-layout">
<div class="demo-screen">

![デモ画面の例](../assets/logo.png)

</div>
<div class="demo-points">

## 注目点

- 操作前の状態
- 主要な操作
- 得られた結果

</div>
</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

# セクション区切り

ここから新しい話題です
