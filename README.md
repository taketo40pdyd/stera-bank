# STERA BANK

支出・収入・予算・支払い予定をひとつにまとめる家計簿アプリ（単一HTMLのPWA）。

## ファイル構成

| ファイル | 役割 |
|---|---|
| `index.html` | アプリ本体（外部ファイル不要） |
| `.nojekyll` | GitHub Pages の Jekyll 処理を無効化 |
| `404.html` | 存在しないURLのときトップへ戻す |
| `robots.txt` | 検索エンジン向け設定 |

## GitHub Pages で公開する手順

1. GitHub で新しいリポジトリを作成（例: `stera-bank`）
2. このフォルダの中身をすべてリポジトリ直下にアップロード（`.nojekyll` も忘れずに）
3. **Settings → Pages → Build and deployment**
   - Source: `Deploy from a branch`
   - Branch: `main` / `/ (root)` → Save
4. 1〜2分後、`https://<ユーザー名>.github.io/<リポジトリ名>/` で公開されます

## 公開後に必ずやること（Googleログインを使う場合）

Firebase コンソール → **Authentication → Settings → 承認済みドメイン** に
`<ユーザー名>.github.io` を追加してください。未設定だとログインがエラーになります。

## 補足

- Firebase の設定値（apiKey など）はWebアプリでは公開される前提の値です。データの保護は
  **Firestore のセキュリティルール**で行います（例: `users/{uid}/**` は本人のみ読み書き可）。
- ログインしない場合は、ブラウザの localStorage に保存されます（端末・ブラウザごとに別データ）。
- ホーム画面に追加すると PWA として全画面で起動できます。
