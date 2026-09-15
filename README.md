# isaok0325.github.io

LoadFlow（と、今後のアプリ）の**プライバシーポリシーとサポートページ**を置くだけの静的サイト。
GitHub Pages のユーザーサイトとして `https://isaok0325.github.io/` で公開する。

> 🟢 **英語（正文）は 2026-09-15 に Founder/CEO 承認済み。** 🔴 **残り5言語の訳が揃うまで公開しない**
> （アプリ内のリンクは言語別なので、揃う前に公開すると日本語の利用者が 404 を踏む）。
> 公開した瞬間から、App Store Connect・AdMob・アプリ本体から参照される正式な文書になる。

## URL（#7 で確定・2026-09-15 Founder/CEO 承認）

| 用途 | URL | 登録先 |
|---|---|---|
| サポート | `https://isaok0325.github.io/loadflow/` | App Store Connect「サポート URL」 |
| プライバシーポリシー（英語・正文） | `https://isaok0325.github.io/loadflow/privacy/` | App Store Connect（英語）／AdMob 同意メッセージ／アプリ本体 |
| 同（各言語） | `…/privacy/{ja,es,ko,zh-Hant,zh-Hans}/` | App Store Connect の各言語 |

🔴 **アプリ本体（`LegalLinks`）の URL はバイナリに焼き込まれる**＝出荷後は審査を通さないと変えられず、
旧バージョンは永久に旧 URL を叩く。**ホストを乗り換えるときは旧 URL を転送で生かしたまま**行うこと。

## 公開のしかた（リポジトリ作成は Founder/CEO）

0. **6言語が揃っているか**と、**`Effective:` の日付が実際の公開日と大きくずれていないか**を見る
1. GitHub で **公開（Public）** リポジトリ `isaok0325.github.io` を作る
   - 🔴 名前は**ユーザー名と完全に一致**させる（これでユーザーサイトになる）
   - 🔴 無料アカウントは **private から Pages を出せない**ので必ず Public
   - 🔴 **README / .gitignore / license を一緒に作らない**（空で作る。作ると push が弾かれる）
2. このディレクトリを push する（**ローカルは init + commit 済み**なので残りは2つ）
   ```sh
   git remote add origin git@github.com:isaok0325/isaok0325.github.io.git
   git push -u origin main
   ```
3. リポジトリの Settings → Pages → Source を **Deploy from a branch / main / (root)** にして Save
4. 数分後に `https://isaok0325.github.io/loadflow/privacy/` が 200 で開くことを確認する（審査時に生きている必要がある）

## 書くときの約束

- 🔴 **外部リソース（Web フォント・CDN・画像・解析タグ）を足さない** — アプリ内の素の `WKWebView` で開かれるため。
  プライバシーポリシーのページ自体が第三者へ通信するのは筋が悪い
- 🔴 **`<meta charset="utf-8">` と viewport を必ず入れる**（charset 無しは `file://` で開いた時だけ化けるので気づきにくい）
- 🔴 **ダークモードを持つ**（アプリは暗い。ライト固定だと設定から開いた瞬間に白く飛ぶ）
- 英語が正文。訳を先に直して英語を放置しない（食い違ったら英語が優先される文書になっている）
- アプリの実装と食い違わせない。特に **Apple Health は v1.0 では書き出しのみ**、**計測は同意後のみ**、**購読者に広告は出ない**
