# Git Reference

## GitHubに新しくPushするときによく使うコマンド
### git remote add origin https://github.com/.../....git
URLにoriginというニックネームを付けるという意味です。  
これをすることによって以降でURLを入力せずとも、originで置き換えることができます。


## リモートリポジトリに自分の変更を反映したい場合
### git push -u origin master
ローカルの内容をoroginというリモートサーバに対してアップロードします。指定するブランチはmaster。  
masterの部分は省略して書かれているので、省略しない場合`master:master`と書きます。
(ローカルmasterからリモートmasterへ)


## リモートリポジトリにpushする前にすること
### git pull

	`git pull origin [pullしたいリモートブランチ名:ローカルブランチ名]`  

pullしたいローカルブランチを省略した場合、現在のブランチにpullされる。  
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


### git diff [origin/master]
git fetch でリモートリポジトリの内容を取得した後、このコマンドを使用することでカレントブランチの内容との差分を表示できる。  
masterと書かれている部分を別のブランチ名に変更すると、そのブランチとの差分を見ることができる。  


## 基本的に使うコマンド
### git branch
ローカルリポジトリに存在するブランチの一覧を表示することができる。  
`--all` リモートブランチの一覧も同時に表示する。  

`git branch [ブランチ名]`でブランチを作成する。  
`-d` 指定したブランチを削除する。  


### git checkout [ブランチ名]
指定したブランチに移動できる。  
`-b git checkout -b [ブランチ名]`で指定したブランチを作成して移動する。  


### git add
作業dirからstageに追加  
`--dry-run` 追加されるファイルを列挙(予行演習)(-n)  


### git commit
stageからコミット履歴に追加  
`-a` 作業dirからコミット履歴に追加  


### git diff
作業dirとstageの変更点を表示  
`--staged` ステージングエリアとコミット履歴の変更点を表示(-s)  


### git log
コミット履歴を表示  
`--shortstat` コミットでの変更点を表示  
`--pretty=oneline` onelieを使用した場合省略される、SHA1IDを詳細表示する  
`--graph` ブランチが視覚化される  
`--decorate` tag,tip,HEAD等が表示される  
`--all` 全てのブランチを表示する  


### git stash save
現在の作業内容を一時保存して、作業ディレクトリを綺麗にする  
作業中に別ディレクトリに移動したい時や、間違えて別のブランチで作業を開始してしまったときに使用する  
スタック領域にスタックされて保存される。  

### git stash pop
`git stash save`でスタックに保存した作業内容を、ポップして上から順番に取得して反映させる。  
保存されているのはスタック領域なので、新しく保存された内容から順番に取得される。  

