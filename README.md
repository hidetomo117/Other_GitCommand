# 作業ブランチ作成からプッシュまで

・ローカルリポジトリ作成

    $ cd your directory
    $ git init
    $ git clone ~~~

・作業ブランチの作成と移動

  	$ git checkout develop
	  $ git pull origin develop
	  $ git branch feature/~~~~ develop
	  $ git checkout feature/~~~~

・作業ブランチのコミット

	  $ git status
	  $ git checkout -- [file that you don't want to add]
	  $ git add --all
	  $ git commit -m "some comment"

・作業ブランチに親ブランチを取り込む

    $ git checkout develop
	  $ git pull origin develop
	  $ git checkout feature/~~~~
	  $ git merge --no-ff develop

・作業ブランチのプッシュ

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
