# 作業ブランチ作成からプッシュまで
(親ブランチ: develop, 作業ブランチ: feature/~~~)

<ローカルリポジトリの作成>

・リモートリポジトリをクローンするため、任意のディレクトリへ移動

    $ cd [リモートリポジトリをクローンするディレクトリ]

・Gitのリポジトリを作成

    $ git init

・リモートリポジトリをローカルへクローン

    $ git clone [リモートリポジトリのクローン用URL]

<最新の親ブランチ取得(リモートにdevelopブランチがあること前提)>

    $ git checkout develop
    $ git pull origin develop

<作業ブランチの作成と移動>

    $ git branch feature/~~~~ develop
    $ git checkout feature/~~~~

<作業ブランチのコミット>

    $ git status
    $ git checkout -- [file that you don't want to add]
    $ git add --all
    $ git commit -m "commit message"

<作業ブランチに親ブランチを取り込む(作業ブランチで作業している間に、developが更新されている可能性があるため)>

    $ git checkout develop
    $ git pull origin develop
    $ git checkout feature/~~~~
    $ git merge --no-ff develop

<作業ブランチのプッシュ>

    $ git push origin feature/~~~~

# よく使うけど忘れるgit command

・git addしたファイルをステージングへ戻す

    $ git reset HEAD [your file　path]

・git addしたファイルを全てステージングへ戻す
	  
    $ git reset HEAD

・ブランチを消す

    $ git branch --delete [your branch name]

・ブランチを強制的に消す

    $ git branch -D [your branch name]

・コミットを消す

    $ git reset --hard HEAD^

・直前のコミットの上書き(commit messageの変更の時とかに使う)

    $ git commit --amend -m "some comment"

# 忘れないけどメモとして残しとくgit command

・変更したファイルを一時保存領域へ退避

    $ git stash

・一時保存領域へ退避したファイルを元に戻す

    $ git stash pop

・リモートブランチの情報をローカルに適応

    $ git fetch --all

・ブランチの一覧を表示

    $ git branch -a
