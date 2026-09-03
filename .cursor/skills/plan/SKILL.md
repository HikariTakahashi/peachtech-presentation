---
name: plan
description: peachtech-ui でタイトルセクション以外の右下にページ番号を表示し、タイトルは非表示のままページ数に含める。Use when /plan が呼ばれたとき、または paginate・ページ番号・タイトルスライドのページ表示を扱うとき。
disable-model-invocation: true
---

# Plan

## 要件（原文）

タイトルセクションを除き、右下にはページ数を表示したいです。
なお、タイトルセクションもページ数に含みます。

## Instructions

`AGENT.md` に従い、Marp標準記法と `peachtech-ui` で実装する。独自記法は追加しない。

1. `slides.md` の frontmatter は `paginate: true` を維持する。
2. ページ番号は `section::after` を右下に置く（既存の左下ロゴと重ねない）。
3. タイトルセクションは `lead` クラスのスライドとする。ページ番号は表示しない。
4. タイトルをページ数から外さない。`_paginate: skip` は使わない。非表示は `_paginate: false` か `section.lead::after { display: none; }` にする。
5. Q&A など `lead` のスライドもタイトルセクションと同じ扱いにする。
6. `template/` の該当スライドも同じ規則に揃える。
7. 変更後は `npm run pdf` と `npm run pptx` を実行して確認する。PowerShell では `&&` を使わない。
