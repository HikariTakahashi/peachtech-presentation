# peachtech-marp-template

Marp for VS Codeを使い、Markdownから16:9の技術発表資料を作るためのOSSテンプレートです。5分程度の発表を想定し、PeachTechの3色だけで構成した `PeachTech UI` テーマ、発表構成例、AI向けプロンプトを同梱しています。

## 対象ユーザー

- エンジニア系大学サークルのメンバー
- Markdown、VS Code、GitHubの基本操作ができる方
- 5分程度の技術発表を準備する方
- AIを使って構成や本文の初稿を作りたい方

## 必要環境

- Node.js 20以上
- npm
- Visual Studio Code
- [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)

コマンド例はnpmを使用します。環境に合わせてpnpm、yarn、bunも利用できますが、lockfileはチーム内で1種類に統一してください。

## リポジトリを使い始める

発表用の作業場所を用意する方法は2つあります。**新しく1つの発表専用リポジトリを作る**場合は **Use this template** を、**テンプレート本体に改善を提案したい**場合は **Fork** を選びます。日常的な発表準備では、テンプレートから新規リポジトリを作る方法を推奨します。

### どちらを選ぶか

| 方法 | 向いている場面 | 注意点 |
|---|---|---|
| **Use this template** | 発表1本につき1リポジトリで管理したい | 元テンプレートとの履歴はつながらない（独立した新規リポジトリになる） |
| **Fork** | テーマやテンプレート自体を改良してPRしたい | fork元との関係が残る。発表原稿だけの管理には向かない場合がある |

### GitHub Template repositoryを使う

1. このリポジトリのGitHub画面を開く。
2. 右上付近の **Use this template** を選ぶ（緑色の **Code** ボタンの隣）。
3. **Create a new repository** を選ぶ。
4. 次を設定する。
   - **Repository name**: 発表タイトルやイベント名が分かる名前（例: `lt-2026-spring-marp`）
   - **Description**: 任意（例: `PeachTech LT 2026春の発表資料`）
   - **Visibility**: 公開・非公開はチームのルールに合わせる
   - **Include all branches**: 通常はオフのままでよい
5. **Create repository** で新しいリポジトリを作成する。
6. 作成後の画面に表示されるURLを使い、ローカルへcloneする。

```bash
git clone https://github.com/YOUR_USER/YOUR_REPO.git
cd YOUR_REPO
```

`YOUR_USER` と `YOUR_REPO` は、作成したリポジトリに合わせて置き換えてください。

### forkする

1. このリポジトリのGitHub画面を開く。
2. 右上の **Fork** を選ぶ。
3. fork先のアカウントや組織、リポジトリ名を確認して **Create fork** する。
4. fork先のリポジトリURLを使い、ローカルへcloneする。

```bash
git clone https://github.com/YOUR_USER/peachtech-marp-template.git
cd peachtech-marp-template
```

forkした場合も、発表原稿の編集はルートの `slides.md` を主対象にします。テンプレート改善のPRを出すときは、fork元の `main`（または既定ブランチ）との差分を意識してください。

### 依存関係を入れる

clone後、リポジトリのルートで次を実行します。

```bash
npm install
```

これにより `@marp-team/marp-cli` が `devDependencies` としてインストールされ、`npm run pdf` などの出力コマンドが使えるようになります。

事前に Node.js のバージョンを確認してください。

```bash
node -v
```

`v20` 以上であることを確認します。未満の場合は [Node.js 公式サイト](https://nodejs.org/) などからアップデートしてください。

インストールが成功したかは、次のいずれかで確認できます。

```bash
# Marp CLI が呼び出せるか
npx marp --version

# サンプル原稿からPDFを生成できるか（dist/slides.pdf が作られる）
npm run pdf
```

### 初回セットアップの確認

依存関係のインストールまで終えたら、次を確認してください。

1. ルートに `slides.md` が存在する（サンプル原稿）。
2. `themes/peachtech-ui.css` と `assets/` がそのまま残っている。
3. VS Code でフォルダを開き、推奨拡張機能の **Marp for VS Code** をインストールする（次のセクション「VS Codeでプレビューする」参照）。

サンプルではなく別の構成から始めたい場合は、`template/` から好みのファイルを `slides.md` にコピーしてから編集します。

PowerShellの例:

```powershell
Copy-Item template/technical-talk.md slides.md
```

macOS / Linuxの例:

```bash
cp template/technical-talk.md slides.md
```

ここまで完了したら、`slides.md` を編集しながらプレビューと出力を試せる状態です。

## VS Codeでプレビューする

このテンプレートは、**VS Code 上で `slides.md` を編集しながらスライドの見え方を確認する**前提で作られています。PDF / PPTX の最終出力は後述の `npm run pdf` などで行いますが、日々の作業はプレビューで崩れや配色を確認しながら進めてください。

### ワークスペースを開く

1. Visual Studio Code を起動する。
2. **File > Open Folder...**（macOS では **ファイル > フォルダーを開く...**）を選ぶ。
3. clone したリポジトリのルートフォルダ（`package.json` と `slides.md` がある階層）を選ぶ。

単一ファイルだけを開く **Open File** では、`.vscode/settings.json` の設定が読み込まれない場合があります。必ずフォルダごと開いてください。

### 推奨拡張機能を入れる

このリポジトリには `.vscode/extensions.json` で **Marp for VS Code**（拡張機能 ID: `marp-team.marp-vscode`）が推奨されています。

1. フォルダを開いた直後、右下または通知に **Install Recommended Extensions** が出たら選ぶ。
2. 出ない場合は、左サイドバーの **Extensions**（`Ctrl+Shift+X` / `Cmd+Shift+X`）を開き、`Marp for VS Code` で検索してインストールする。
3. マーケットプレイス: [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)

インストール後、拡張機能が有効であることを確認してください（拡張機能一覧で **Disable** ではなく **Enable** になっている状態）。

### ワークスペースを信頼する

初回にフォルダを開いたとき、**Restricted Mode（制限モード）** の通知が出ることがあります。このテンプレートでは次の理由で、**信頼できるワークスペースとして開く**ことを推奨します。

- `.vscode/settings.json` で `markdown.marp.html` を `all` に設定し、2カラムなど **HTML レイアウト**を使えるようにしている
- `themes/peachtech-ui.css` が `assets/logo.png` を参照している
- スライド本文から `assets/` 配下の **ローカル画像**を読み込む

信頼しない場合、テーマ・ロゴ・画像・HTML レイアウトがプレビューで正しく表示されないことがあります。通知の **Trust** / **Manage** から、このフォルダを信頼済みに設定してください。

### 自動適用される VS Code 設定

リポジトリ同梱の `.vscode/settings.json` は、次をワークスペースに適用します。

| 設定 | 値 | 意味 |
|---|---|---|
| `markdown.marp.themes` | `./themes/peachtech-ui.css` | `PeachTech UI` テーマを Marp プレビューに登録する |
| `markdown.marp.html` | `all` | Marp スライド内の HTML タグを許可する |

`slides.md` 冒頭の `theme: peachtech-ui` と組み合わさり、プレビューでも CLI 出力と同じテーマで表示されます。テーマを変えたい場合は frontmatter とこの設定の両方を揃えてください。

### プレビューを開く

Marp for VS Code には **`Marp: Open Preview` という専用コマンドはありません**。`marp: true` が有効な Markdown を、**VS Code 標準の Markdown プレビュー**で開くと、Marp のスライド表示になります。

1. エクスプローラーから `slides.md` を開く。
2. 冒頭の frontmatter に `marp: true` があることを確認する（このテンプレートの `slides.md` には最初から入っています）。
3. 次のいずれかでプレビューを開く。

**方法A: エディター右上のアイコン**

- エディター右上の **プレビューアイコン**（分割画面のマーク）をクリックする。
- 横に開きたい場合は、プレビューアイコン付近の **Open Preview to the Side** を選ぶ。

**方法B: キーボードショートカット**

| 操作 | Windows / Linux | macOS |
|---|---|---|
| プレビューを開く | `Ctrl+Shift+V` | `Cmd+Shift+V` |
| 横にプレビューを開く | `Ctrl+K` のあと `V` | `Cmd+K` のあと `V` |

**方法C: コマンドパレット**

1. `Ctrl+Shift+P`（macOS: `Cmd+Shift+P`）でコマンドパレットを開く。
2. 次のいずれかを実行する。
   - **Markdown: Open Preview**
   - **Markdown: Open Preview to the Side**

コマンドパレットでは `Markdown` と入力して絞り込むと見つけやすいです。`Marp` で検索してもプレビュー用コマンドは出ません（Marp 固有の操作は **Export slide deck...** など別コマンドです）。

**Marp 用の操作メニュー（エクスポートなど）**

- エディター右上の **Marp アイコン**（Marp のロゴ）から、エクスポートや `marp: true` の切り替えなどを選べます。
- コマンドパレットでは `markdown.marp.export`（**Export slide deck...**）や `markdown.marp.toggleMarpFeature` などが利用できます。

> **注意: 他の Markdown プレビュー拡張機能**
>
> **Markdown Preview Enhanced** など、別の Markdown プレビュー拡張を入れていると、標準プレビューが置き換わり、スライドではなく通常の Markdown 表示になることがあります。その場合は次を試してください。
>
> - コマンドパレットから明示的に **Markdown: Open Preview to the Side** を実行する
> - 競合する拡張機能を無効化する、またはプレビュー用ショートカットの割り当てを見直す
>
> 参考: [marp-team/marp-vscode の Issue #82](https://github.com/marp-team/marp-vscode/issues/82)

プレビューが Marp スライドとして動いているときは、スライドごとに区切られた見た目になり、編集中の位置に応じて該当スライドがハイライトされます。

### Cursor でプレビューする（重要）

**Cursor** では、内蔵の Markdown エディター（リッチ表示 / Preview モード）が標準の Markdown プレビューと別系統です。**Marp for VS Code は VS Code 標準プレビューに載せる拡張**のため、Cursor の内蔵プレビューだけを使っていると、**いつも普通の Markdown 表示のまま**になります。

次の手順で **テキストエディター + 標準 Markdown プレビュー** を使ってください。

1. **Marp for VS Code** を Cursor の拡張機能からインストールする（未導入なら）。
2. `slides.md` のタブを **右クリック** → **Reopen Editor With...**（エディターを別の方法で開き直す）→ **Text Editor** を選ぶ。
   - 画面上部に **Markdown / Preview** の切り替えが見えている場合も、まず Text Editor に戻す。
3. `Ctrl+Shift+P` → **Markdown: Open Preview to the Side** を実行する。
4. エディター右上に **Marp のアイコン**が出ていれば、拡張が `marp: true` を認識しています。

このリポジトリの `.vscode/settings.json` では、`.md` を最初からテキストエディターで開く設定（`workbench.editorAssociations`）を入れています。フォルダを開き直すと、手順2が不要になる場合があります。

**Cursor で拡張プレビューが使えないときの代替**

エディター内プレビューがどうしても Marp にならない場合は、CLI で HTML を出してブラウザで確認します（テーマ・レイアウトは提出物に近い表示です）。

```bash
npm run html
```

生成された `dist/slides.html` をブラウザで開く。編集のたびにコマンドを再実行してください。

プレビュー作業を Cursor より安定させたい場合は、同じフォルダを **Visual Studio Code** で開いて作業する方法もあります。

### 編集しながら確認するコツ

- **保存のたびにプレビューが更新**される。見え方が変わらないときは一度 `Ctrl+S` / `Cmd+S` で保存する。
- **スライド区切り**は `---` 。1枚のスライドだけ直したいときは、その前後の `---` を誤って消さないよう注意する。
- **ページ番号・ロゴの有無**はスライドごとの HTML コメント（例: `<!-- _class: lead no-logo -->`）で変わる。タイトルスライドは枠なしのピンク背景で、左下のロゴと右下のページ番号は出ない。本文スライドでは左下にロゴと「PeachTech」、右下に緑背景の「現在ページ / 合計」が出る。タイトルもページ数には含む。
- **Presenter Notes**（`<!-- ... -->` で書く発表メモ）は、プレビュー画面上には通常表示されない。HTML 出力のプレゼンタービューで確認する（「Presenter Notes」セクション参照）。

### プレビューで確認すべきこと

提出前や長い編集のあとは、プレビューで次をざっと確認してください。

- テーマ色（白背景・桃色の外枠・黒文字・緑の見出し下線）が意図どおりか
- 左下のロゴと「PeachTech」の表示 / 非表示（タイトルは非表示、`no-logo` クラス）が想定どおりか
- 2カラム・画像・コードブロックがはみ出していないか
- 1スライドに情報が詰め込みすぎていないか

プレビューは最終成果物の近似ですが、フォントや細かいレイアウトは PDF / PPTX とわずかに異なる場合があります。提出直前は `npm run pdf` と `npm run pptx` の出力も必ず確認してください。

### うまく表示されないとき

| 症状 | 確認すること |
|---|---|
| テーマが白一色・素の Markdown 風になる | `slides.md` の frontmatter に `marp: true` と `theme: peachtech-ui` があるか。フォルダごと開いているか |
| ロゴや画像が出ない | ワークスペースを信頼しているか。パスが `assets/...` の相対パスか。ファイルが存在するか |
| HTML 2カラムが崩れる | 制限モードのままではないか。`template/layouts.md` の記法と揃っているか |
| プレビューが通常の Markdown のまま | **Cursor** なら上記「Cursor でプレビューする」を参照。Text Editor で開き直してから **Markdown: Open Preview to the Side** を実行する |
| プレビューが開かない | Marp for VS Code が有効か。`slides.md` を Text Editor で開いているか。VS Code / Cursor を再起動する |
| 拡張プレビューが諦められない | `npm run html` で `dist/slides.html` をブラウザ表示する |

それでも解決しない場合は、拡張機能を一度無効化して再有効化するか、VS Code のバージョンを最新に近づけてから再度試してください。

## `slides.md` を編集する

冒頭のfrontmatterは基本的に維持してください。

```md
---
marp: true
theme: peachtech-ui
size: 16:9
paginate: true
---
```

スライド間は `---` で区切ります。内容は1スライド1メッセージを目安にし、長い説明は発表時の口頭説明やPresenter Notesへ分けます。

テーマには次のクラスを用意しています。

- `lead`: タイトルやQ&A向け（枠なし・ピンク背景・白文字。左下ロゴとページ番号は出ない。ページ数には含める）
- `section`: セクション区切り向け（枠なし・ピンク背景・白文字。ページ番号は出ない。ページ数には含める）
- `no-logo`: そのスライドだけ左下のロゴと「PeachTech」を隠す
- `columns`: 2カラムの親要素
- `image-center`: 画像を中央に配置
- `code-focus`: コードを大きく表示
- `compact`: 本文を少し小さく表示
- `media-split`: 画像と説明を左右に配置（`reverse` を追加すると左右反転）
- `stat-layout`: 大きな数値と測定条件を並べる
- `process`: 4段階の処理フローを表示
- `architecture`: システム構成を階層で表示
- `code-compare`: 修正前後のコードを比較
- `demo-layout`: デモ画面と注目点を並べる

タイトルスライドでロゴとページ番号を隠す例（`skip` は使わない。番号は非表示でもページ数に含む）:

```md
<!-- _class: lead no-logo -->
<!-- _paginate: false -->
```

## テンプレートを使う

`template/` には次の例があります。

- `template/basic.md`: 最小構成
- `template/technical-talk.md`: 5分の技術発表構成
- `template/layouts.md`: 基本レイアウトと、画像＋説明、数値・成果、処理フロー、アーキテクチャ、コード比較、デモ画面

使いたいファイルを `slides.md` にコピーして編集します。詳しくは `template/README.md` を参照してください。

## AIで初稿を作る

`template/ai-prompt.md` の入力欄を埋め、ChatGPT、Codex、Claude、GitHub Copilot Chat、GeminiなどのAIに渡してください。特定のAIを推奨するものではありません。

生成されたMarkdownは、そのまま採用せず次を確認してください。

- frontmatterと `---` の区切りが正しいか
- 発表時間に収まる情報量か
- 数値、固有名詞、参考資料が正しいか
- 画像の利用条件と出典に問題がないか
- VS CodeプレビューとPDF/PPTX出力で崩れていないか

AIエージェントがリポジトリを直接編集する場合の共通ルールは `AGENT.md` にあります。

## PDF / PPTX / HTMLを出力する

```bash
# PDF（必須）
npm run pdf

# PowerPoint（必須）
npm run pptx

# HTML（任意）
npm run html

# 3形式をまとめて生成
npm run export
```

出力先は固定です。

| 形式 | 出力ファイル       |
| ---- | ------------------ |
| PDF  | `dist/slides.pdf`  |
| PPTX | `dist/slides.pptx` |
| HTML | `dist/slides.html` |

`dist/` は生成時に自動作成され、Git管理の対象外です。ローカル画像を読み込むため、スクリプトは信頼できる原稿に対してのみ `--allow-local-files` を使用します。

## 画像を置く

画像は `assets/` 配下に置き、Markdownから相対パスで参照します。

```md
![画面構成の説明](assets/example.png)
```

ファイル名は内容が分かる英数字とハイフンを推奨します。画像の著作権、ライセンス、必要な出典表記を確認してください。

## Presenter Notes

Marp標準のPresenter Notesは、対象スライド内のHTMLコメントとして記述します。ディレクティブと解釈されない普通の文章にしてください。

```md
# デモ

操作手順を短く表示します。

<!--
ここで30秒のデモを行う。
失敗時は assets/demo-fallback.png を表示する。
-->
```

HTML出力を開いた場合はプレゼンタービューからノートを確認できます。ノートはHTMLソースに含まれるため、外部共有前に機密情報がないか確認してください。独自のノート機能は実装していません。

## デザイン

テーマIDは `peachtech-ui`、表示名は **PeachTech UI** です。外部フォントは使わず、システムフォントを使用します。ブランド色は次の3色、本文は黒です。

- white: `#ffffff`
- peach: `#f09dc1`
- green: `#3fb585`
- black: `#000000`

通常スライドは白背景・桃色の外枠・黒文字です。見出しは太字に緑の下線、タイトルスライド（`lead`）は枠なしのピンク背景・白文字です。タイトル以外のスライドでは左下にロゴと通常ウェイトの「PeachTech」、右下に緑背景・白文字の「現在ページ / 合計」を表示します。

## ロゴのライセンス例外

`assets/logo.png` と `assets/logo.svg` はMIT Licenseの対象外です。これらのロゴは、本テンプレートを用いて作成するプレゼンテーション内でのみ利用できます。再配布、改変、商標・サービスの識別目的など、それ以外の利用は許可されません。詳細は `assets/README.md` を参照してください。

## ライセンス

ロゴの例外を除くソースコードと文書はMIT Licenseです。詳細は `LICENSE` を参照してください。

## 行動規範

参加者同士を尊重し、差別、嫌がらせ、威圧的な言動を行わないでください。技術レベルや経験の違いを前提に、建設的で具体的なフィードバックを心がけてください。問題が起きた場合は公開の場で個人を攻撃せず、リポジトリ管理者へ連絡してください。

## コントリビューション

IssueやPull Requestを歓迎します。テーマカラー、Marp標準記法、生成物、ロゴ例外に関するルールは `CONTRIBUTING.md` を確認してください。
