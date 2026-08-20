# blog-assets

わたしの今の最適解（はてなブログ / Blogger）のブログ記事で使う、AI生成ストック画像の置き場所。

**Publicリポジトリです。** 記事本文にそのまま埋め込む画像なので、非公開にする理由がありません
（`raw.githubusercontent.com` のURLをそのまま `<img src="...">` に使うため、Publicである必要があります）。
機密情報（APIキー・トークンなど）は絶対にこのリポジトリに置かないでください。

## 使い方

1. ジャンルに合ったフォルダ（`mobile` / `subscription` / `furusato` / `lifestyle` / `pointactivity` / `ev`）に画像を追加する
   - ファイル名は `キーワードが分かる英数字-連番.jpg`（例: `sim-card-hands-01.jpg`）
   - 目安: 1600×900px前後、JPEG、500KB以下
2. `blog-automation` リポジトリの `config/image_library.json` に、画像のURLとマッチさせたいキーワードを追記する
   - URL形式: `https://raw.githubusercontent.com/yk-yuha/blog-assets/main/<フォルダ>/<ファイル名>`
3. `fetch_image.py` が記事生成時にこのライブラリを先にチェックし、マッチする画像があればそれを使う
   （マッチしなければ今まで通りPexelsから自動取得）

## フォルダ = ジャンル対応

| フォルダ | ジャンル |
|---|---|
| `mobile` | 格安SIM・モバイル回線の乗り換え |
| `subscription` | サブスク動画・音楽配信サービス |
| `furusato` | ふるさと納税ポータル |
| `lifestyle` | 生活便利サービス（ウォーターサーバー・宅配クリーニング等） |
| `pointactivity` | ポイ活・キャッシュレス決済アプリ |
| `ev` | EV・Tesla関連（手動投稿記事用） |
