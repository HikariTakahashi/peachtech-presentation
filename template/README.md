# テンプレート集

用途に近いMarkdownをルートの `slides.md` にコピーしてから編集してください。

| ファイル | 用途 |
|---|---|
| `basic.md` | 最小構成から始める |
| `technical-talk.md` | 5分の技術発表を組み立てる |
| `layouts.md` | レイアウトの実装例を確認する |
| `ai-prompt.md` | AIに初稿を生成させる |

PowerShellの例:

```powershell
Copy-Item template/technical-talk.md slides.md
```

macOS / Linuxの例:

```bash
cp template/technical-talk.md slides.md
```

コピー後はVS Codeで `slides.md` を開き、Marpプレビューで確認してください。
