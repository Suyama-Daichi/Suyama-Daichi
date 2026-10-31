# d0nchan portfolio

d0nchan（どんちゃん）の個人ポートフォリオサイト。ビルド不要の静的サイトで、GitHub Pages にそのまま公開する。

## 構成

- `index.html` — トップ（About / Work / Homelab / Writing / Contact）
- `metrandom.html` / `swarmlytics.html` / `kakitome.html` / `homelab.html` — 実績の詳細ページ
- `assets/` — 画像（アイコン・スクリーンショット・OGP 画像）
- `404.html` / `favicon.svg` / `apple-touch-icon.png`
- `.nojekyll` — Jekyll の処理を止めるための空ファイル。消さない

CSS はすべて各 HTML のインライン style と `<head>` 内の `<style>` に書かれている。フォントは Google Fonts（Inter / Noto Sans JP / JetBrains Mono）。JavaScript は使っていない。

## 守ること

- **本名を出さない。** 表記は「d0nchan」「d0nchan（どんちゃん）」だけ。メールアドレスも載せない。GitHub のリンク（github.com/Suyama-Daichi）だけは本人の判断で残している
- 文言は推敲済み。勝手に書き換えない。直す必要があると思ったら、変更案を出して確認を取る
- デザインはミニマル・モノクロ（#111111 / #3A3A3A / #6B6B6B / #E5E5E5 / #FFFFFF）。色やフォントを増やさない
- リンクはすべて相対パスにする。`https://suyama-daichi.github.io/<リポジトリ名>/` 配下で動くように、`/` から始まる絶対パスは使わない
- スマホ幅（390px）で横スクロールが出ないこと

## 公開手順（GitHub Pages）

1. このフォルダ（GitHub プロフィール用リポジトリ Suyama-Daichi/Suyama-Daichi と同居）を master ブランチに push する
2. リポジトリの Settings → Pages → Build and deployment で、Source を「Deploy from a branch」、Branch を `master` / `/ (root)` にする
3. 数分後に `https://suyama-daichi.github.io/Suyama-Daichi/` で公開される

公式ドキュメント:
- GitHub Pages サイトを作成する: https://docs.github.com/ja/pages/getting-started-with-github-pages/creating-a-github-pages-site
- 公開元を設定する: https://docs.github.com/ja/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## 残っている作業（TODO）

1. ~~**OGP / Twitter カード**~~（済: 公開 URL は https://suyama-daichi.github.io/Suyama-Daichi/）:各ページに `og:title` `og:description` `og:image` `og:url` `twitter:card` を足す。`og:image` と `og:url` は絶対 URL が必要なので、公開 URL が決まってから入れる。OGP 画像（1200×630）はモノクロのデザインに合わせて作る
2. ~~**favicon**~~（済: `favicon.svg` / `apple-touch-icon.png`）: `d0nchan` の頭文字などで、モノクロの favicon（SVG と 180px の apple-touch-icon）を作って各ページに設定する
3. ~~**404.html**~~（済）: トップへ戻るリンクだけのシンプルな 404 ページを作る
4. ~~**画像の最適化**~~（済）: `assets/` の PNG（swarmlytics-map / trip / search）は 200KB 超。WebP に変換して参照を差し替える。`<img>` に `width` / `height` と、ファーストビュー外の画像には `loading="lazy"` を付ける
5. **インライン style の整理（任意）**: 同じ style が繰り返されている。見た目を変えずに共通の CSS ファイルへまとめる。やる場合は、変更前と変更後のスクリーンショットを 1440px と 390px で比べて差がないことを確かめる
6. ~~**リンク切れの確認**~~（済: 2026-10-31 に全17件が HTTP 200）: 外部リンク（X / GitHub / Blog / App Store / Google Play / 各記事）が開けるか確かめる

## 確認のしかた

```sh
npx serve .   # または python3 -m http.server
```

1440px と 390px の両方で全ページを開き、画像が表示されること、横スクロールが出ないこと、ナビゲーションのリンク先が正しいことを確かめる。
