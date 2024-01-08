# 出題１：Gitについて
Gitはバージョン管理システム（VCS）の１つである。他のVCSとの違いは、他のVCSでは起点となるファイルの集合とそれぞれのファイルに時間の経過とともに加えられた変更の情報つまり差分情報を格納していくが、Gitでは起点となるファイルの集合を格納したあとは差分を格納するのではなくその時点のファイルの状態（スナップショット）を時系列にコミット（記録）していく。コミットを貯めていく場所はリポジトリという。<br>
ファイルに変更が無い場合は、Gitはファイルを再格納せず、既に格納してある以前の同一のファイルへのリンクを格納する。  
便利な点は以下のとおりである。<br>
コミットするタイミングはユーザーが決められる。バージョン管理をローカルPCのリポジトリ（ローカルリポジトリ）で行えるためネットワーク障害が起きても影響を受けない。複数人と共同作業する場合は、ローカルリポジトリで作業した結果をサーバー上のリモートリポジトリにコミットすればよい。さらに、リモートリポジトリから他者と共同作業した最新バージョンを自分のローカルリポジトリに取得して作業を行うこともできる。

# 出題２：GitHubについて
GitHubはGitリポジトリのホスティングサービスである。インターネット上でGitHubのサーバー内にリモートリポジトリを作成し複数人での共同作業が可能となる。デフォルトでは「プライベート」設定となり指定した特定のユーザだけがアクセスできる。誰にでも閲覧できる状態にするには「パブリック」設定とする。2019年よりプライベート（非公開）リポジトリは無料となっている。<br>
ローカルPCとネットワークを接続するため安全にアクセスできるようにSSH（Secure Shell）プロトコルと公開鍵を用いたサーバー認証を行う。<br>
便利な点は以下のとおりである。<br>
リモートリポジトリ作成のために自分でメンテナンスする必要のある有料サーバーを用意する必要がなく、GitHubにアカウントを登録すれば無料でインターネット上でGitを使用できリモートリポジトリを作成できる。インターネット接続が可能な環境であれば、場所を選ばずに共同作業が可能である。無料であっても公開範囲をプライベートまたはパブリックを選択できる。 
# 出題３：Markdownについて
HTMLのように書式設定要素（見出し、段落、箇条書きなど）をプレーンテキストにて記載して文書を書くためのマークアップ言語である。Markdown 形式のファイルを作成するときは、Markdown 構文をテキストに追加していく。<br>
Markdown 構文とは、例えば、課題１を見出しとするには見出し「課題１」の前にシャープ記号と半角空白１つを追加する（例：# 課題１）。見出しの階層を下げたい場合はシャープ記号を増やしていく（例：## 課題１−１）。文の一部を太字にするには、その前後に 2 つのアスタリスクを半角空白なしで追加する（例：文の一部を\*\*太字\*\*にするには）。<br>
Visual Studio Codeを使用すると、記載したMarkdown 形式プレーンテキストをプレビューで見え方を確認することができる。  
GitHub向けのMarkdownとしてGitHub Flavored Markdownがある。基本的なMarkdownの文法に、GitHub 用文法を追加したものである。プルリクエストや Issue を作ったり、それにコメントしたりするときに便利である。
# 出題４：１〜３をREADME.mdにまとめてリモートリポジトリに公開する
# 出題５：記録
# -gitとは
### 🔵 2023/2/4
>
>https://git-scm.com/book/ja/v2/ から日本語版ProGit.pdfをダウンロードし目次と前書きを印刷する。<br>
>- 目次と前書きを読み、Gitの基本概念を理解するために該当すると思われる目次のタイトルにマークしておく。それ以外は実際に使用する際のコマンドなどであると考える。
>- 課題の進め方をまとめる。
>- 本格的に課題に取り組む前はメモで記録を取っていく。<br><br>

>前書きを読み、先に知りたく興味のある10章を読むこととする。

>#### 🔹🔹 バージョン管理システムについてのメモ
>https://tracpath.com/bootcamp/learning_git_firststep.html
バージョン管理システム入門(初心者向け)<br><br>
バージョン管理とは、一つのファイルやファイルの集合に対して時間とともに加えられていく変更（追加、変更、削除）を記録するシステムで、後で特定バージョンを呼び出すことができるようにするためのもので、歴史の古い順に「**ローカル・バージョン管理システム**」「**集中バージョン管理システム**」「**分散バージョン管理システム**」の大きく３つの方式がある。  
>>##### ⚫︎ローカル・バージョン管理システム<br>
>>バージョン管理下のファイルに対する全ての変更を保持するシンプルなデータベースによるものて。もっとも有名なVCSツールの一つは、RCSと呼ばれるシステムである。 
このツールは基本的に、リビジョン間のパッチ(ファイル間の差分) の集合を特殊なフォーマットでディスク上に保持するという仕組みで動いている。<br>
任意のファイルについて、それが過去の任意の時点でどういうものだったかということを、パッチを重ね上げていくことで再現することができる。<br> 
>>##### ⚫︎集中バージョン管理システム
>>他のシステムを使う開発者との共同作業を可能にするために、集中゙バージョン管理システム(CVCS)が開発された。<br>
CVS、Subversion、Perforceなどがあるが、それらはバージョン管理されたファイルを全て持つ一つのサーバーと、その中心点からファイルをチェックアウトする多数のクライアントからなっている。長年の間、これはバージョン管理の標準であった。<br>
利点は、プロジェクトメンバが何をしているのか、全員がある程度わかる。管理者は、誰が何をできるのかについて、きめ細かくコントロールできる。また、一つのCVCSを管理するのは、全てのクライアントのローカル・データベースを取り扱うより、ずっと簡単である。<br>
深刻なマイナス面は、中央サーバーが1時間の間停止すると、その1時間の間は全員が、共同作業も全くできず、作業中のものにバージョンをつけて保存をすることもできなくなる。もし中央データベースのあるハードディスクが破損し、適切なバックアップが保持されていなければ、完全に全てを失ってしまう。<br> 
ローカルVCSシステムも、これと同じ問題がある。つまり、一つの場所にプロジェクトの全体の履歴を持っていると、全てを失うリスクが常にある。<br>
>>##### ⚫︎分散バージョン管理システム
>>DVCS(Git、Mercurial、Bazaar、Darcsのようなもの)では、クライアントはファイルの最新スナップショットをチェックアウト(訳者注:バージョン管理 システムから、作業ディレクトリにファイルやディレクトリをコピーすること)するだけではない。リポジトリ(訳者注:バージョン管理の対象になるファイル、ディレクトリ、更新履歴などの一群)全体をミラーリングする。そのため、あるサーバーが故障して、DVCSがそのサーバーを介して連携していたとしても、いずれかのクライアント・リポジトリの一つをサーバーにコピーすれば修復できる。クローンは全て、実際は全データの完全バックアップである。<br>
>>これらのDVCSの多くは、複数のリモート・リポジトリで作業をするということがうまく扱えるようになっているので、異なった方法で異なる人々のグループと同時に同じプロジェクト内で共同作業することができる。このため、階層モデルなどの、集中システムでは不可能な幾つかのワークフローが構築できるようになっている。 


>#### 🔸🔸 Gitと他VCSとの違い
>スナップショットで、差分ではない。<br>
>Gitと他のVCS (Subversionとその類を含む)の主要な相違は、Gitのデータについての考え方である。概念的には、他のシステムのほとんどは、情報をファイルを基本とした変更のリストとして格納する。これらのシステム(CVS、Subversion、Perforce、Bazaar等々)は、システムが保持しているファイルの集合と、時間を通じてそれぞれのファイルに加えられた変更の情報を考える。 
Gitはデータをミニ・ファイルシステムのスナップショットの集合のように考える。Gitで全てのコミット(訳注:commitとは変更を記録・保存するGitの操作。)をするとき、もしくはプロジェクトの状態を保存するとき、Gitは基本的に、その時の全てのファイルの状態のスナップショットを撮り、そのスナップショットへの参照を格納する。効率化のため、ファイルに変更が無い場合は、Gitはファイルを再格納せず、既に格納してある、以前の同一のファイルへのリンクを格納する。

>#### 🔸🔸 なぜGitを使うべきなのか
>Gitのほとんどの操作は、ローカル・ファイルと操作する資源だけ必要とする。大体はネットワークのコンピューターからの情報は必要ではない。プロジェクトの履歴は丸ごとローカル・ディスクに保持している。<br>
Gitはサーバーに履歴を取得しに行って表示する必要がない。あるファイルの現在のバージョンと、そのファイルの1ヶ月前の間に導入された変更点を知りたいのであれば、1か月前の ファイルを調べてローカルで差分の計算を行なえる。<br>
このことはまた、オフラインであるか、VPNから切り離されていたとしても、できない事は非常に少ないことを意味する。<br>
Gitの全てのものは、格納される前にチェックサムが取られ、その後、そのチェックサムで照合される。これは、Gitがそれに関して感知することなしに、あらゆるファイルの内容を変更することが不可能であることを意味する。この機能は、Gitの最下層に組み込まれている。Gitがそれを感知できない状態で、転送中に情報を失う、もしくは壊れたファイルを取得することはない。<br>
Gitは通常はデータを追加するだけ 
Gitで行動するとき、ほとんど全てはGitデータベースにデータを追加するだけです。 システムにいかなる 方法でも、UNDO不可能なこと、もしくはデータを消させることをさせるのは困難です。 あらゆるVCSと同様 に、まだコミットしていない変更は失ったり、台無しにできたりします。 

しかし、スナップショットをGitに 
コミットした後は、特にもし定期的にデータベースを他のリポジトリにプッシュ(訳注:pushはGitで管理す るあるリポジトリのデータを、他のリポジトリに転送する操作。詳細は後の章を参照)していれば、変更を失 うことは大変難しくなります。 
三つの状態 
今、注意してください。 もし学習プロセスの残りをスムーズに進めたいのであれば、これはGitに関して覚え ておく主要な事です。 Gitは、ファイルが帰属する、コミット済、修正済、ステージ済の、三つの主要な 状態を持ちます。 コミット済は、ローカル・データベースにデータが安全に格納されていることを意味しま す。 修正済は、ファイルに変更を加えていますが、データベースにそれがまだコミットされていないことを 意味します。 ステージ済は、次のスナップショットのコミットに加えるために、現在のバージョンの修正さ れたファイルに印をつけている状態を意味します。 
このことは、Gitプロジェクト(訳者注:ディレクトリ内)の、Gitディレクトリ、作業ディレクトリ、ステー ジング・エリアの三つの主要な部分(訳者注:の理解)に導きます。 
基本的なGitのワークフローは、このような風に進みます: 1. 作業ディレクトリのファイルを修正します。 
2. 修正されたファイルのスナップショットをステージング・エリアに追加して、ファイルをステージしま す。 
3. コミットします。(訳者注:Gitでは)これは、ステージング・エリアにあるファイルを取得し、永久不 変に保持するスナップショットとしてGitディレクトリに格納することです。 
もしファイルの特定のバージョンがGitディレクトリの中にあるとしたら、コミット済だと見なされます。 も し修正されていて、ステージング・エリアに加えられていれば、ステージ済です。 そして、チェックアウト されてから変更されましたが、ステージされていないとするなら、修正済です。 Git の基本では、これら の状態と、どうやってこれらを利用をするか、もしくは完全にステージ化部分を省略するかに関してより詳し く学習します。 

#### 🔹🔹　分かったこと、疑問に思ったこと
GITはバージョン管理システム（VCS）の１つであること。
従来のバックアップとどう違うのか？
他のVCSには何があるのか?

ファイル群のローカル・バージョン管理システム
中バージョン管理システム

GITはバージョン管理システム（VCS）の１つである。
バージョン管 理とは、一つのファイルやファイルの集合に対して時間とともに加えられていく変更（追加、変更、削除）を記録するシステムで、 後で特定バージョンを呼び出すことができるようにするためのもの で、歴史の古い順に「ローカル・バージョン管理システム」、「集中バージョン管理システム」「分散バージョン管理システム」の大きく３つの方式がある。

GITは「分散バージョン管理システム」である。

疑問
自動的に履歴を残すことが可能であるのか、その場合随時となるが定期的な時間でバックアップを取るのか、また全てのバックアップ？
変更のあった箇所だけのバックアップとすると、変更のなかった箇所との統合はどのようにされるのか？

便利な点
自分が履歴を残したいという時点で履歴が残せること。自由度がある。


### 2023/7/9
参考サイト
https://qiita.com/showmeear/items/ee61984089445e52f794
学生のための卑近な git・GitHub 入門


https://eh-career.com/engineerhub/entry/2022/03/31/093000
Gitの教え方に困った！非エンジニアにも「いい感じ」でわかるGitの解説


https://tracpath.com/bootcamp/learning_git_firststep.html
バージョン管理システム入門(初心者向け)
https://tracpath.com/bootcamp/learning_git_firststep.html


スナップショットで、差分ではない
他のシステムのほとんどは、情報をファイルを基本とした変更のリストとして格納します 

効率化のため、ファイルに変更が無い場合は、Gitはファイルを再 格納せず、既に格納してある、以前の同一のファイルへのリンクを格 

プロジェクトの履歴を閲覧するために、Gitはサーバーに履歴を取得しに行って表示する必要があり ません。直接にローカル・データベースからそれを読むだけ 


### 2023/9/18
「いちばんやさしいGit&GitHubの教本」でまずは復習
従来の定時刻にバッチによるバックアップのイメージが邪魔をしていたため、自分の意思でその時点での対象となる全ファイルの状態を保存するというのは目から鱗
つまりコミットの単位やタイミングは自由に決められる。

GITは「バージョン管理システム」の一つ。
ファイルの変更をバージョンとして記録し、記録した地点にいつでも戻れる。
作業者が複数人いても、ファイルの最新状態や変更の履歴をわかりやすく保てる。
大きな特徴は、大規模プロジェクトを高速に、そして複数人で並行して扱えるような仕組みをもっている。
誰でも無償で使える。
ユーザーが任意のタイミングで、管理対象となっている全ファイルのその時点での状態（記録）を保存する。この操作を「コミット」するという。
ファイルの状態に加え、操作を行なったユーザーや時刻の情報も記録される。
便利な点：いつ、どのような単位（区切り）でコミットするかは自分で決められるのでプログラムのソースコードであれば「機能Aを追加したコミット」と「機能Bを追加したコミット」を分けておけば、履歴の行き来により「機能Aだけの状態」「機能Bだけの状態」などにあとから切り替えることが容易になる。また、コミットがきれいに分割されていることにより、他の人が履歴を追いやすくなる。
リポジトリはコミットの保管庫

GitHubは、Gitの仕組みを利用して、インターネット上でのスムーズな共同作業を可能にしたWebサービス。

### 2023/10/14
時間を空けすぎて以前試したまでを確認
久しぶりにVS Codeを立ち上げようとLaunchpadで検索するがヒットせず。
確認するとダウンロードフォルダに入ったままでアプリケーションに移動していなかったのでアプリケーションに移動して改めてLaunchpadから選択できることを確認。
WebのGitの日本語訳ではわかりにくいため該当箇所を「いちばんやさしいGit&GitHubの教本」と照らし合わせて確認する。

今一度、他のVCSとの違いを明確にしておく

## -gitインストール
### 2023/8/12
最新バージョンのGitでかつTerminalを使用するためGitのウェブサイト http://git-scm.com/download/mac からダウンロードする。

現時点、最新バージョンは2.41.0であるが、
Binalyでは2.33.oと記載されているにも関わらず違いにすぐに気づかずBinalyでインストールしてしまった。

一旦　rm '/usr/local/bin/git'　を実行して削除した。
インストールのやり直し
Homebrewをインストールして　brew install git 　を実行してGitのインストールを試みたところ以下のエラーが出たが、リンクの問題であることをすぐに理解できず
最後の行にあった  rm '/usr/local/bin/git'　を実行し、再度　brew install git 　を実行する。

==> Pouring git--2.41.0_2.ventura.bottle.1.tar.gz
Error: The `brew link` step did not complete successfully
The formula built, but is not symlinked into /usr/local
Could not symlink bin/git
Target /usr/local/bin/git
already exists. You may want to remove it:
  rm '/usr/local/bin/git'

次に出たメッセージはWarningでgit 2.41.0_2 はすでにインストール済みでリンクされていないとあり　braw link git を実行すればリンクできるということでbrew link gitを実行したところ　'usr/local/bin/git-cvsserver'　がすでに存在する
エラーとなる。
rm 'usr/local/bin/git-cvsserver' を実行すればよいとのことでこのコマンドを実行する
その後、再度　brew link --overwrite gitを実行したところ
バージョン2.41.0に更新された。

## -gitセットアップ
### 2023/8/16
VS Codeのインストール
日本語環境インストール
VS Codeターミナルからgit のバージョンを確認。
先日のMacのターミナルから確認したバージョンと同じであることを確認。
git version 2.41.0

管理したいフォルダを作成
progit.pdfでわかりにくい箇所を「図解！Git&GitHubのツボとコツがゼッタイにわかる本」で確認しながら進める。

### 2022/9/20
gitにユーザー名とパスワードを設定する。

設定：git config --global user.name ユーザー名

設定：git config --global user.email メールアドレス

Visual Studio Codeをコマンドラインから呼び出せるようにする。
利用するエディタをVisual Studio Codeとする設定をする。


## -gitの使い方
- ### git init
### 2024/1/6
ターミナルでの操作
ホームディレクトリに情報通信ネットワークの課題用フォルダmau_ntwk_kadaiを作成する
mau_ntwk_kadaiに移動してローカルリポジトリを作成する
progit.pdfでわかりにくい箇所を「図解！Git&GitHubのツボとコツがゼッタイにわかる本」で確認しながら進める。
Terminalでmau_ntwk_kadaiに移動してローカルリポジトリを作成する
git init 
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint: git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint: git branch -m <name>

Initialized empty Git repository in /Users/dragon/mau_ntwk_kadai/.git/
.gitフォルダが作成された

ターミナル以外でも.gitディレクトリの存在をmacのFinderで確認したい
隠しフォルダを表示する　コマンド＋シフト＋ピリオド
.gitフォルダ内の中身を確認
思った以上にフォルダ、ファイルが作成されていた

Git statusでローカルリポジトリの状態を見る
dragon@dragonnoMacBook-Pro mau_ntwk_kadai % git status
On branch master

No commits yet

Untracked files:
(use "git add <file>..." to include in what will be committed)
.DS_Store

nothing added to commit but untracked files present (use "git add" to track)
dragon@dragonnoMacBook-Pro mau_ntwk_kadai % 

- ### git add
### 2024/1/6
git addを行なってワークツリーに入っている。
まだGIT管理下にはファイルが登録されていない。
README.mdファイルをステージングエリアに登録する

git add README.md

On branch main

No commits yet

Changes to be committed:
(use "git rm --cached <file>..." to unstage)
new file: README.md


- ### git commit
### 2024/1/6
[main (root-commit) 6203a58] 第１回：READMEファイル作成
1 file changed, 17 insertions(+)
create mode 100644 README.md



git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
(use "git branch --unset-upstream" to fixup)

nothing to commit, working tree clean

ブランチの概念
ブランチとは？
ここで新たに知らない単語が出てきた。

### 2024/1/8
git logでコミットの履歴を確認する
commit d9ed51bbd58f3f86e133e61a9145e793a3ac4349 (HEAD -> main)
Author: mohashifrom201710 <m.ohashi.yogi@gmail.com>
Date:   Mon Jan 8 16:26:00 2024 +0900

    第２回：記録を追加
    
    出題５の内容として記録を追加する

commit 6203a58cc6af08d07110e71a2818309c10985c48 (origin/main)
Author: mohashifrom201710 <m.ohashi.yogi@gmail.com>
Date:   Sun Jan 7 15:53:48 2024 +0900

    第１回：READMEファイル作成
    
    テスト用フォルダ内に作成したある程度推敲した出題１〜３までの内容で作成する


- ### git push
### 2024/1/6
プッシュで変更をリモートリポジトリに反映する
git push の後ろにはブランチ名を指定したがエラーとなった。

git push main
fatal: 'main' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.

git push origin main
が正しい。
確かに、リモートリポジトリ自体の名称を指定する必要があった。
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 1.94 KiB | 1.94 MiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:MOyogi201710-MAU202401/mau-j2n.git
* [new branch] main -> main

## -githubアカウントの作成
### 2023/10/22
GitHubのアカウントを決める際、個人情報を考慮し決め方についてネットで調べた
自由に設定できる
全角文字の場合
半角英数字を使う
は個人が特定
複数のGitアカウントを使いわける

Globalを使うか使わないかの違いがわかった


### 2024/1/4
GitHubにアカウント登録しmau-j2nリポジトリを作成した。
SSHキーを作成：タイトルはforMAU

ssh -T git@github.comで正しくSSHキーを設定できたかを確認した。
Hi MOyogi201710-MAU202401! You've successfully authenticated

## -githubへの公開方法
### 2023/11/19
Visual Studio CodeでMarkdownファイルを作成する。
test_Markdown.md

### 2024/1/7
GitHubのリポジトリをローカルPCにクローンする
git clone git@github.com:MOyogi201710-MAU202401/mau-j2n.git

ローカルPCにおいて作成しておいたREADME.mdをクローンしたリポジトリに保存する

リモートリポジトリの設定をローカルPCのTerminalから確認する。
git remote -v
origin git@github.com:MOyogi201710-MAU202401/mau-j2n.git (fetch)
origin git@github.com:MOyogi201710-MAU202401/mau-j2n.git (push)

「origin」はクローン元のリモートリポジトリを表す。
教本によると、名称を変更することができる。用途としては複数のリポジトリを扱う場合にそれぞれに名称を設定することとする。

git statusで現状を確認する。

On branch main

No commits yet

Untracked files:
(use "git add <file>..." to include in what will be committed)
README.md

nothing added to commit but untracked files present (use "git add" to track)
