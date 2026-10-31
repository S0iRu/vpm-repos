# S0iRu VPM Packages

S0iRu の VRChat 向けパッケージを配る VPM リポジトリです。zip はそれぞれのパッケージリポジトリの GitHub Release にあり、このリポジトリは一覧だけを GitHub Pages で配信します。

追加ページ: https://s0iru.github.io/vpm-repos/

ページの「ALCOM / VCC にこのリポジトリを追加」は `vcc://vpm/addRepo` を開き、ALCOM または VCC のリポジトリ追加へ進みます。Windows では、最後に vcc リンクを登録したアプリが開きます。

手で追加する場合の URL:

```
https://s0iru.github.io/vpm-repos/index.json
```

## パッケージを足す

1. パッケージリポジトリの直下、または Simple Folder Icon のように `Packages/<パッケージ名>` に VPM 用の `package.json` を置く。
2. このリポジトリの `source.json` の `githubRepos` に `owner/repo` を1行追加する。
3. パッケージリポジトリから `.github/workflows/publish-package.yml` を呼ぶ。`package.json` の version を上げてデフォルトブランチへ push すると、GitHub Release と zip が作られる。同じ version の Release がある push は配信しない。
4. 上流のフォークなら、`site/forks.json` にパッケージ ID と元リポジトリを書く。一覧ページに「○○ のフォーク」と出る。

プレリリースのバージョンは、プロジェクト側でプレリリースパッケージを表示するとインストールできます。

Release の直後に一覧を更新するには、パッケージリポジトリの secret `LISTING_DISPATCH_TOKEN` に、このリポジトリの Actions を起動できる PAT を設定します。未設定でも Release は成功し、一覧は毎日 0:00（日本時間）か Actions の手動実行で更新されます。
