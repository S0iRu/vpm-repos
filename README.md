# S0iRu VPM Packages

S0iRu の VRChat 向けパッケージを配る VPM リポジトリです。zip はそれぞれのパッケージリポジトリの GitHub Release にあり、このリポジトリは一覧だけを GitHub Pages で配信します。

ALCOM または VCC に追加する URL:

```
https://s0iru.github.io/vpm-repos/index.json
```

## パッケージを足す

1. パッケージリポジトリの直下に VPM 用の `package.json` を置く。
2. GitHub Release に、次の2つの資産を付ける。
   - `package.json`
   - `{パッケージ名}-{バージョン}.zip`（zip の直下に `package.json` があること）
3. このリポジトリの `source.json` の `githubRepos` に `owner/repo` を1行追加して push する。

プレリリースのバージョンは、プロジェクト側でプレリリースパッケージを表示するとインストールできます。

パッケージのリリース直後に一覧を更新するには、パッケージリポジトリの secret `LISTING_DISPATCH_TOKEN` に、このリポジトリの Actions を起動できる PAT を設定します。未設定でも、このリポジトリの日次ビルドか Actions の手動実行で一覧は更新されます。
