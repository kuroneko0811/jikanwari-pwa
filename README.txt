円グラフ時間割（PWA版）の公開手順
====================================

このフォルダの中身（index.html / manifest.webmanifest / sw.js / icons フォルダ）を
そのままWebに置くと、スマホのホーム画面に「アプリ」として追加できます。
いちばん手軽な無料の方法は GitHub Pages です。

■ GitHub Pages で公開する（無料）
1. https://github.com でアカウントを作り、ログインする
2. 右上の「＋」→「New repository」
   - Repository name：jikanwari（半角英数字なら何でもOK）
   - 「Public」を選んで「Create repository」
3. 作成後の画面で「uploading an existing file」をクリック
4. このフォルダの中身（index.html、manifest.webmanifest、sw.js、icons フォルダ）を
   まとめてドラッグ＆ドロップ →「Commit changes」
   ※ フォルダごとではなく「中身」を入れてください。index.html が一番上の階層にあればOK
5. リポジトリの「Settings」→ 左メニュー「Pages」
   - Source：Deploy from a branch
   - Branch：main / (root) →「Save」
6. 1〜2分待つと、同じ画面に公開URLが出ます
   例）https://あなたのユーザー名.github.io/jikanwari/

※ Public リポジトリなので、アプリのプログラムは誰でも見られます。
  予定データはスマホ本体に保存されるので、URLを知られても予定は見えません。

■ スマホに入れる
iPhone：Safari で公開URLを開く → 共有ボタン →「ホーム画面に追加」
Android：Chrome で公開URLを開く → メニュー →「アプリをインストール」または「ホーム画面に追加」

一度開けば、そのあとは電波がなくても使えます。

■ これまでの予定を引っ越す
Claude上のツールとアプリ版は、データの保存場所が別です。
1. Claude上のツール下部「データのバックアップ・読み込み」→「テキストをコピー」
2. メールやメモアプリなどでスマホにそのテキストを送る
3. アプリ版の同じ欄に貼り付けて「貼り付けた内容を読み込む」

■ アプリを更新するとき
index.html などを差し替えたら、sw.js の 1 行目付近にある
  const CACHE = "jikanwari-v1";
の数字を v2, v3 … と上げてからアップロードしてください。
次にアプリを開いたとき（2回目の起動から）新しい版になります。
