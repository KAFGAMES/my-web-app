git add .

git commit -m "バグ修正"

git push

\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\




git remote -v

git remote set-url origin https://github.com/KAFGAMES/my-web-app.git

git push origin main

git status






git rm -r --cached .
git add docs/
git add my-web-app/

git commit -m "Clear cache and add files properly"
git push


mv index.html .
git add index.html
git commit -m "Move index.html to root"
git push origin main


git clone リポジトリのURL
git add .
git commit -m "変更内容の説明"

最新のリポジトリをプルする（競合防止） GitHub上で他の端末からも作業が進んでいる場合があるため、プッシュする前にリモートリポジトリの最新状態を取得（プル）することが重要です。

bash
コードをコピーする
git pull origin main
ここで競合が発生する可能性がありますが、Gitは競合する箇所を表示してくれるので、手動で解決します。競合解決後、再度コミットします。

bash
コードをコピーする
git commit -m "競合を解決しました"
変更をリモートにプッシュする プルで競合が解決されたら、変更をGitHubにアップロード（プッシュ）します。

bash
コードをコピーする
git push origin main



\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
ワークツリーの未コミットの変更をすべて破棄：
git restore .

Google Chromeの場合:
ブラウザのメニューを開く：画面右上の3つの縦ドットをクリックします。
「設定」を選択：メニューから「設定」をクリック。
「プライバシーとセキュリティ」を選択：左側のメニューから「プライバシーとセキュリティ」を選びます。
「閲覧履歴データの削除」をクリック：このオプションを選んでください。
「詳細設定」タブに切り替える：ここで削除するデータの範囲を選択できます。
「Cookies と他のサイトデータ」の項目を選択：これにチェックを入れて、「データを削除」をクリックすると、ローカルストレージもクリアされます。

\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\

1. PlanetScaleのセットアップ
PlanetScaleのアカウントを作成: PlanetScaleの公式サイトにアクセスし、無料アカウントを作成します。
新しいデータベースの作成: ダッシュボードから「Create Database」を選択して新しいデータベースを作成します。
ブランチの作成: PlanetScaleはGitのようなブランチ管理機能を持っています。最初のブランチを作成してデータベースに接続できる状態にします。
接続情報の取得: 作成したデータベースに接続するための「Connection Details」（接続情報）を確認し、これを後で使います。MySQLクライアント、Node.js、または他の言語から接続可能です。
2. VSCODEでプログラミングを始める
VSCODEのインストール: まだインストールしていない場合は、Visual Studio Codeをダウンロードしてインストールします。

Node.jsプロジェクトの作成（例としてNode.jsを使用する場合）:

VSCODEで新しいフォルダを作成し、ターミナルを開きます。
npm init -y コマンドで新しいNode.jsプロジェクトを初期化します。
MySQLライブラリをインストールします：npm install mysql2。
PlanetScaleに接続するコードの作成:

app.js などのファイルを作成し、以下のようにMySQLデータベースに接続します。
javascript
コードをコピーする
const mysql = require('mysql2');

const connection = mysql.createConnection({
    host: 'your-planetscale-host',
    user: 'your-username',
    password: 'your-password',
    database: 'your-database'
});

connection.connect((err) => {
    if (err) {
        console.error('Error connecting to the database:', err);
        return;
    }
    console.log('Connected to PlanetScale!');
});
クエリの実行: 接続が成功したら、データベースに対してクエリを実行し、データを取得・挿入するコードを作成できます。

\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\