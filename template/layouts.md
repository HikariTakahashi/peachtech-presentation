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

<!-- _class: section -->
<!-- _paginate: false -->

# セクション区切り

ここから新しい話題です
