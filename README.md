# 作業ブランチ作成からプッシュまで
(親ブランチ: develop, 作業ブランチ: feature/~~~)

<ローカルリポジトリの作成>

    - リモートリポジトリをクローンするため、任意のディレクトリへ移動

      $ cd [リモートリポジトリをクローンするディレクトリ]

    - Gitのリポジトリを作成

      $ git init

    - リモートリポジトリをローカルへクローン

      $ git clone [リモートリポジトリのクローン用URL]

<最新の親ブランチ取得(リモートリポジトリにdevelopブランチがあること前提)>

    - リモートリポジトリにdevelopブランチがある場合、以下のコマンドを実行すると
      リモートリポジトリのdevelopブランチがローカルリポジトリに引っ張ってこれる

      $ git checkout develop
    
    - リモートリポジトリとローカルリポジトリに差異があると困るので、
      念の為リモートリポジトリのdevelopブランチの情報をローカルリポジトリのdevelopへ引っ張ってくる
    
      $ git pull origin develop

<作業ブランチの作成と移動>

    - 親ブランチdevelopから作業ブランチfeature/~~~を作成

      $ git branch feature/~~~~ develop
    
    - 親ブランチdevelopから作業ブランチfeature/~~~へ移動
    
      $ git checkout feature/~~~~

<作業ブランチのコミット>

    - ファイルの変更状況を確認
    
      $ git status

    - 誤って変更したファイルがある場合、以下のコマンドで取り消しを実行
      (変更を全て破棄する場合は git checkout -- .)

      $ git checkout -- [変更を破棄したいファイル名]

    - 変更したファイルをステージングへ追加

      $ git add --all

    - コミットメッセージ(どんな変更を行ったか)を記載し、コミットを実行

      $ git commit -m "変更した内容をここへ記載"

<作業ブランチに親ブランチを取り込む(作業ブランチで作業している間に、developが更新されている可能性があるため)>

    - 作業ブランチfature/~~~から親ブランチdevelopへ移動

      $ git checkout develop
    
    - リモートリポジトリからローカルリポジトリへ、最新のdevelopの情報を引っ張ってくる
    
      $ git pull origin develop
    
    - 親ブランチdevelopから作業ブランチfeature/~~~へ移動
    
      $ git checkout feature/~~~~
    
    - 作業ブランチfeature/~~~に親ブランチdevelopの内容を取り込む
      (コンフリクトが起きた場合は別途対応)
    
      $ git merge --no-ff develop

<作業ブランチのプッシュ>

    - 作業ブランチfeature/~~~はローカルリポジトリにしか存在しないため、
      以下のコマンドでローカルリポジトリへ反映させる
    
      $ git push origin feature/~~~~

# よく使うけど忘れるgit command

- git addしたファイルをステージングへ戻す

      $ git reset HEAD [your file　path]

- git addしたファイルを全てステージングへ戻す
	  
      $ git reset HEAD

- ブランチを消す

      $ git branch --delete [your branch name]

- ブランチを強制的に消す

      $ git branch -D [your branch name]

- コミットを消す

      $ git reset --hard HEAD^

- 直前のコミットの上書き(commit messageの変更の時とかに使う)

      $ git commit --amend -m "some comment"

# 忘れないけどメモとして残しとくgit command

- 変更したファイルを一時保存領域へ退避

      $ git stash

- 一時保存領域へ退避したファイルを元に戻す

      $ git stash pop

- リモートブランチの情報をローカルに適応

      $ git fetch --all

- ブランチの一覧を表示

      $ git branch -a
