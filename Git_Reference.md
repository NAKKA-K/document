# Git Reference

## GitHubに新しくPushするときによく使うコマンド
### git remote add origin https://github.com/.../....git
	URLにoriginというニックネームを付けるという意味です。
	これをすることによって以降でURLを入力せずとも、originで置き換えることができます。


## リモートリポジトリに自分の変更を反映したい場合
### git push -u origin master
	ローカルの内容をoroginというリモートサーバに対してアップロードします。指定するブランチはmaster。
	masterの部分は省略して書かれているので、省略しない場合master:masterと書きます。(ローカルmasterからリモートmasterへ)


## リモートリポジトリにpushする前にすること
### git pull
	pullするとローカルに変更がない場合、fast-forword-margeされる。その場合、そのままpushできる。
	ローカルに変更があった場合、競合する。競合したときはファイルの
	<<<HEAD
	===
	>>>sample
	の部分を直した後、commitする。


## リモートリポジトリの内容だけを見たい場合
### git fetch
	リモートリポジトリの最新の履歴の取得だけを行うことができます。
	取得したコミットは名前のないブランチとして取り込まれます。
	このブランチにはFETCH_HEADという名前でチェックアウトすることができます。
	この状態からfetchした内容をローカルに統合する場合は、FETCH_HEADをmarge、又はpullを実行します。
	pullとは内部でfetch + margeをしています。そのためmargeと同じ履歴になります。


## その他のコマンド
### echo 文字の出力
	-n 最後の改行を除く
	>> ファイルの最後に追加

### git diff 作業dirとstageの変更点を表示
	--staged ステージングエリアとコミット履歴の変更点を表示(-s)

### git commit stageからコミット履歴に追加
	-a 作業dirからコミット履歴に追加

### bash file.sh shellを実行

### git add 作業dirからstageに追加
	--dry-run 追加されるファイルを列挙(予行演習)(-n)

### git log    コミット履歴を表示
	--shortstat コミットでの変更点を表示
	--pretty=oneline onelieを使用した場合省略される、SHA1IDを詳細表示する
	--graph ブランチが視覚化される
	--decorate tag,tip,HEAD等が表示される
	--all 全てのブランチを表示する

