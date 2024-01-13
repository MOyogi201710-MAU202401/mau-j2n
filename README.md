# 🔴🔴 Google Chromeのビューアーでご覧いただく際には、翻訳の設定は「英語」のままでお読み願います。<br>「日本語」にしますと日本語文が意図しない日本語に自動翻訳されるためです。
![GoogleChrome翻訳設定](GoogleChrome翻訳設定.png)<br><br>
# 🔴 情報通信ネットワーク　通信授業第１課題
# １：Gitについて
Gitはバージョン管理システム（VCS）の１つである。他のVCSとの違いは、他のVCSでは起点となるファイルの集合とそれぞれのファイルに時間の経過とともに加えられた変更の情報つまり差分情報を記録していくが、Gitでは起点となるファイルの集合を記録したあとは差分ではなくその時点のファイルの状態（スナップショット）を時系列にコミット（記録）していく。コミットを蓄積していく場所をリポジトリという。<br>
ファイルに変更が無い場合は、Gitはファイルを再記録せず、既に記録してある以前の同一のファイルへのリンクを記録する。  
便利な点は以下のとおりである。<br>
コミットするタイミングはユーザーが決められる。バージョン管理をローカルPCのリポジトリ（ローカルリポジトリ）で行えるためネットワーク障害が起きても影響を受けない。複数人と共同作業する場合は、ローカルリポジトリで作業した結果をサーバー上のリモートリポジトリにコミットすればよい。さらに、リモートリポジトリから他者と共同作業した最新バージョンを自分のローカルリポジトリに取得して作業を行うこともできる。
# ２：GitHubについて
GitHubはGitリポジトリのホスティングサービスである。インターネット上でGitHubのサーバー内にリモートリポジトリを作成し複数人での共同作業が可能となる。デフォルトでは「プライベート」設定となり指定した特定のユーザだけがアクセスできる。誰にでも閲覧できる状態にするには「パブリック」設定とする。2019年よりプライベート（非公開）リポジトリは無料となっている。<br>
ローカルPCとネットワークを接続するため安全にアクセスできるようにSSH（Secure Shell）プロトコルと公開鍵を用いたサーバー認証を行う。<br>
便利な点は以下のとおりである。<br>
リモートリポジトリ作成のために自分でメンテナンスする必要のある有料サーバーを用意する必要がなく、GitHubにアカウントを登録すれば無料でインターネット上でGitを使用できリモートリポジトリを作成できる。インターネット接続が可能な環境であれば、場所を選ばずに共同作業が可能である。無料であっても公開範囲をプライベートまたはパブリックを選択できる。 
# ３：Markdownについて
HTMLのように書式設定要素（見出し、段落、箇条書きなど）をプレーンテキストで記載して文書を書くためのマークアップ言語である。Markdown 形式のファイルを作成するときは、Markdown 構文をテキストに追加していく。<br>
Markdown 構文とは、例えば、課題１を見出しとするには見出し「課題１」の前にシャープ記号と半角空白１つを追加する（例：# 課題１）。見出しの階層を下げたい場合はシャープ記号を増やしていく（例：## 課題１−１）。文の一部を太字にするには、その前後に 2 つのアスタリスクを半角空白なしで追加する（例：文の一部を\*\*太字\*\*にするには）。<br>
Visual Studio Codeを使用すると、記載したMarkdown 形式プレーンテキストをプレビューで見え方を確認することができる。  
GitHub向けのMarkdownとしてGitHub Flavored Markdownがある。基本的なMarkdownの文法に、GitHub 用文法を追加したものである。プルリクエストや Issue を作ったり、それにコメントしたりするときに便利である。
# ４：１〜３をREADME.mdにまとめてリモートリポジトリに公開する
# ５：記録
# -🔴gitとは
### 🔵 $\textcolor{blue}{\text{2023/2/4}}$
https://git-scm.com/book/ja/v2/ から日本語版ProGit.pdfをダウンロードし目次と前書きを印刷する。<br.>
- 目次と前書きを読み、Gitの基本概念を理解するために該当すると思われる目次のタイトルにマークしておく。それ以外は実際に使用する際のコマンドなどであると考える。
- 課題の進め方をまとめる。
- 本格的に課題に取り組む前はメモで記録を取っていく。
前書きを読み、先に知りたく興味のある10章を読むこととする。
#### 🔸🔸　疑問に思ったこと
- 従来のバックアップとどう違うのか？
- 他のVCSには何があるのか?
- 自動的に履歴を残すことが可能であるのか、その場合随時となるが定期的な時間でバックアップを取るのか、また全てのバックアップ？
#### 🔹🔹 バージョン管理システムについてのメモ
https://tracpath.com/bootcamp/learning_git_firststep.html<br>
バージョン管理システム入門(初心者向け)<br>
バージョン管理とは、一つのファイルやファイルの集合に対して時間とともに加えられていく変更（追加、変更、削除）を記録するシステムで、後で特定バージョンを呼び出すことができるようにするためのものである。<br>
歴史の古い順に「**ローカル・バージョン管理システム**」「**集中バージョン管理システム**」「**分散バージョン管理システム**」の大きく３つの方式がある。  
##### ⚫︎ローカル・バージョン管理システム
バージョン管理下のファイルに対する全ての変更を保持するシンプルなデータベースによるもので、もっとも有名なVCSツールの一つは、RCSと呼ばれるシステムである。<br>
このツールは基本的に、リビジョン間のパッチ(ファイル間の差分) の集合を特殊なフォーマットでディスク上に保持するという仕組みで動いている。<br>
任意のファイルについて、それが過去の任意の時点でどういうものだったかということを、パッチを重ね上げていくことで再現することができる。
##### ⚫︎集中バージョン管理システム
他のシステムを使う開発者との共同作業を可能にするために、集中゙バージョン管理システム(CVCS)が開発された。<br>
CVS、Subversion、Perforceなどがあるが、それらはバージョン管理されたファイルを全て持つ一つのサーバーと、その中心点からファイルをチェックアウトする多数のクライアントからなっている。長年の間、これはバージョン管理の標準であった。<br>
利点は、プロジェクトメンバが何をしているのか、全員がある程度わかる。管理者は、誰が何をできるのかについて、きめ細かくコントロールできる。また、一つのCVCSを管理するのは、全てのクライアントのローカル・データベースを取り扱うより、ずっと簡単である。<br>
深刻なマイナス面は、中央サーバーが1時間の間停止すると、その1時間の間は全員が、共同作業も全くできず、作業中のものにバージョンをつけて保存をすることもできなくなる。<br>もし中央データベースのあるハードディスクが破損し、適切なバックアップが保持されていなければ、完全に全てを失ってしまう。<br>
ローカルVCSシステムも、これと同じ問題がある。つまり、一つの場所にプロジェクトの全体の履歴を持っていると、全てを失うリスクが常にある。
##### ⚫︎分散バージョン管理システム
DVCS(Git、Mercurial、Bazaar、Darcsのようなもの)では、クライアントはファイルの最新スナップショットをチェックアウト(訳者注:バージョン管理 システムから、作業ディレクトリにファイルやディレクトリをコピーすること)するだけではない。<br>
リポジトリ(訳者注:バージョン管理の対象になるファイル、ディレクトリ、更新履歴などの一群)全体をミラーリングする。そのため、あるサーバーが故障して、DVCSがそのサーバーを介して連携していたとしても、いずれかのクライアント・リポジトリの一つをサーバーにコピーすれば修復できる。クローンは全て、実際は全データの完全バックアップである。<br>
これらのDVCSの多くは、複数のリモート・リポジトリで作業をするということがうまく扱えるようになっているので、異なった方法で異なる人々のグループと同時に同じプロジェクト内で共同作業することができる。このため、階層モデルなどの、集中システムでは不可能な幾つかのワークフローが構築できるようになっている。 
#### 🔸🔸 Gitと他VCSとの違い
スナップショットであって、差分ではない。<br><br>
概念的には、他のシステムのほとんどは、情報をファイルを基本とした変更のリストとして格納する。これらのシステム(CVS、Subversion、Perforce、Bazaar等々)は、システムが保持しているファイルの集合と、時間を通じてそれぞれのファイルに加えられた変更の情報を考える。<br>
![CVS、Subversion、Perforce、Bazaar等々](CVS等.png)<br><br>
Gitはデータをミニ・ファイルシステムのスナップショットの集合のように考える。<br>
![Git](Git.png)<br><br>
Gitで全てのコミットをするとき、もしくはプロジェクトの状態を保存するとき、Gitは基本的に、その時の全てのファイルの状態のスナップショットを撮り、そのスナップショットへの参照を格納する。効率化のため、ファイルに変更が無い場合は、Gitはファイルを再格納せず、既に格納してある、以前の同一のファイルへのリンクを格納する。<br>
プロジェクトの履歴は丸ごとローカル・ディスクに保持しているため、Gitはサーバーに履歴を取得しに行って表示する必要がない。<br>
あるファイルの現在のバージョンと、そのファイルの1ヶ月前の間に導入された変更点を知りたいのであれば1か月前のファイルを調べてローカルで差分の計算を行なえる。<br>
つまり、**オフラインであるか、VPNから切り離されていたとしても、バージョン管理はローカルで行える**。<br>
Gitの全てのものは、格納される前にチェックサムが取られ、その後、そのチェックサムで照合される。これは、Gitがそれに関して感知することなしに、あらゆるファイルの内容を変更することが不可能であることを意味する。<br>
この機能は、Gitの最下層に組み込まれている。Gitがそれを感知できない状態で、転送中に情報を失う、もしくは壊れたファイルを取得することはない。<br>
Gitはほとんど全てはGitデータベースにデータを追加するだけで、UNDOも削除もできない。ただし、まだコミットしていないファイルの内容は変更も削除も可能である。
#### 🔸🔸 基本的なGitのワークフロー
Gitの管理対象フォルダの中には.gitという隠しフォルダが作成される。ここがローカルリポジトリの場所である。<br>
このローカルリポジトリでファイルの編集からコミットまでを行うこととなる。<br>
ローカルリポジトリにコミットを行いファイルの状態を保存するには、「ワークツリー」「ステージングエリア」「Gitディレクトリ」と呼ばれる場所を用いる。<br>
1. ワークツリーのファイルを修正する。
    - 編集の開始地点となる。「ワークツリー」「ワーキングツリー」「作業ディレクトリ」と呼ばれる。
    - 最後にコミットした状態から手が加わっていない「unmodified（変更されていない）」状態にある。ここで何らかの編集をすると「modified（変更済み）」となる。 
2. ワークツリー内の編集後の内容をステージングエリアに登録する。
    - 「modified（変更済み）」の状態から「staged（ステージングエリアに追加済み）」の状態に変わる。 
3. ステージングエリア内のファイルをGitディレクトリにコミットする。
    - 一度コミットにより記録された内容は変更・削除されない。仮にあとからコミットを取り消す操作を行うと、取り消す前後の状態が記録として残るため、コミット自体がなかったことにはならない。
    
![GitWorkFlow](GitWorkFlow.png)<br><br>

コミットによりファイルの状態は再び「unmodified（変更されていない）」状態となる。
なお、新規ファイルを作成した場合のファイルの状態は「untracked（追跡されていない）」状態であり、まだ一度もコミットされたことのないファイルのため、Git管理下に置かれていない。
### 🔵 $\textcolor{blue}{\text{2023/7/9}}$
参考サイト<br><br>
https://qiita.com/showmeear/items/ee61984089445e52f794<br>
学生のための卑近な git・GitHub 入門<br><br>
https://eh-career.com/engineerhub/entry/2022/03/31/093000<br>
Gitの教え方に困った！非エンジニアにも「いい感じ」でわかるGitの解説<br><br>
https://tracpath.com/bootcamp/learning_git_firststep.html<br>
バージョン管理システム入門(初心者向け)<br>

サイトの内容を参考資料として読む。 
### 🔵 $\textcolor{blue}{\text{2023/9/18}}$
### 「いちばんやさしいGit&GitHubの教本」でまずは復習する。
会社のシステムによりバッチ処理でバックアップされるイメージが邪魔をしていたため、自分の意思でその時点での対象となる全ファイルの状態を保存できるというのは目から鱗であった。<br>
つまり**コミットの単位やタイミングは自由に決められる**。<br>
- GITは「バージョン管理システム」の一つ。
ファイルの変更をバージョンとして記録し、記録した地点にいつでも戻れる。
作業者が複数人いても、ファイルの最新状態や変更の履歴をわかりやすく保てる。
大きな特徴は、大規模プロジェクトを高速に、そして複数人で並行して扱えるような仕組みをもっている。
- リポジトリはコミットの保管庫である。
- 誰でも無償で使える。
- ユーザーが任意のタイミングで、管理対象となっている全ファイルのその時点での状態（記録）を保存する。この操作を「コミット」するという。
- ファイルの状態に加え、操作を行なったユーザーや時刻の情報も記録される。
- 【便利な点】<br>
 いつ、どのような単位（区切り）でコミットするかは自分で決められるのでプログラムのソースコードであれば「機能Aを追加したコミット」と「機能Bを追加したコミット」を分けておけば、履歴の行き来により「機能Aだけの状態」「機能Bだけの状態」などにあとから切り替えることが容易になる。また、コミットがきれいに分割されていることにより、他の人が履歴を追いやすくなる。
- GitHubは、Gitの仕組みを利用して、インターネット上でのスムーズな共同作業を可能にしたWebサービス。
### 🔵 $\textcolor{blue}{\text{2023/10/14}}$
時間を開けすぎた。<br>
以前試したところまでを確認する。<br>
久しぶりにVS Codeを立ち上げようとLaunchpadで検索するがヒットせず。<br>
確認するとダウンロードフォルダに入ったままでアプリケーションに移動していなかったのでアプリケーションに移動して改めてLaunchpadから選択できることを確認する。<br>
WebのGitの日本語訳ではわかりにくいため該当箇所を「いちばんやさしいGit&GitHubの教本」と照らし合わせて確認する。<br>

今一度、他のVCSとの違いを明確にしておく。

# -🔴gitインストール
### 🔵 $\textcolor{blue}{\text{2023/8/13}}$
最新バージョンのGitでかつTerminalを使用するためGitのウェブサイト http://git-scm.com/download/mac からダウンロードする。<br>

現時点、$\textcolor{blue}{\text{最新バージョンは2.41.0}}$ であるが、
$\textcolor{red}{\text{Binalyでは2.33.0}}$ と記載されているにも関わらず違いにすぐに気づかず $\textcolor{red}{\text{Binalyでインストールしてしまった}}$ 。<br>
一旦　rm '/usr/local/bin/git'　を実行して削除する。<br><br>
$\textcolor{red}{\text{HomebrewでGitインストールのやり直しを行う}}$ 準備をする。<br>
Homebrewをインストール後　**brew install git** 　を実行してGitのインストールを試みたところ、以下のエラーが出たが、リンクの問題であることをすぐに理解できず、エラーメッセージ文の最後の行にあった  **rm '/usr/local/bin/git'**　を実行し、再度　**brew install git** 　を実行する。

==> Pouring git--2.41.0_2.ventura.bottle.1.tar.gz<br>
Error: The `brew link` step did not complete successfully<br>
The formula built, but is not symlinked into /usr/local<br>
Could not symlink bin/git<br>
Target /usr/local/bin/git<br>
already exists. You may want to remove it:<br>
  rm '/usr/local/bin/git'<br>

次に出たメッセージはWarningでgit 2.41.0_2 はすでにインストール済みでリンクされていないとあり　**braw link git** を実行すればリンクできるということで **brew link git** を実行したところ、**'usr/local/bin/git-cvsserver'　がすでに存在する**　エラーとなる。<br><br>
$\textcolor{blue}{\text{rm 'usr/local/bin/git-cvsserver}}$ <br>を実行すればよいとのことでこのコマンドを実行する。<br>
その後、再度　$\textcolor{blue}{\text{brew link --overwrite git}}$ を実行したところ<br><br>
$\textcolor{blue}{\text{バージョン2.41.0に更新された。}}$
# -🔴gitセットアップ
### 🔵 $\textcolor{blue}{\text{2023/8/16}}$
- VS Codeのインストール
- 日本語環境インストール

VS Codeターミナルからgit のバージョンを確認する。<br>
先日のMacのターミナルから確認したバージョンと同じであることを確認する。<br>
**git version 2.41.0**

まずはGitテスト用のフォルダを作成する。<br>
progit.pdfでわかりにくい箇所を「図解！Git&GitHubのツボとコツがゼッタイにわかる本」で確認しながら進める。

### 🔵 $\textcolor{blue}{\text{2023/9/20}}$
- gitにユーザー名とパスワードを設定する。<br>
設定：**git config --global user.name ユーザー名**<br>
設定：**git config --global user.email メールアドレス**<br>
- Visual Studio Codeをコマンドラインから呼び出せるようにする。<br>
- 利用するエディタをVisual Studio Codeとする設定をする。<br>
# -🔴gitの使い方
- ## -🔴git init
### 🔵 $\textcolor{blue}{\text{2024/1/6}}$
**Macターミナルでの操作**
- ローカルPCのホームディレクトリに情報通信ネットワークの課題用フォルダ **mau_ntwk_kadai** を作成する。
progit.pdfでわかりにくい箇所を「図解！Git&GitHubのツボとコツがゼッタイにわかる本」で確認しながら進める。
- Terminalで mau_ntwk_kadai に移動して **git init** を実行して**ローカルリポジトリを作成する**。

**git init**<br>
hint: Using 'master' as the name for the initial branch. This default branch name<br>
hint: is subject to change. To configure the initial branch name to use in all<br>
hint: of your new repositories, which will suppress this warning, call:<br>
hint: <br>
hint: git config --global init.defaultBranch `<name>`<br>
hint: <br>
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and<br>
hint: 'development'. The just-created branch can be renamed via this command:<br>
hint: <br>
hint: git branch -m `<name>`<br><br>
**gitフォルダが作成されたことを確認する**<br>
ターミナル以外でも.gitディレクトリの存在をmacのFinderで確認したい。<br>
隠しフォルダを表示するには　**コマンド＋シフト＋ピリオド**　と打つ。<br>
- gitフォルダ内の中身を確認する。
思った以上にフォルダ、ファイルが作成されている。<br>

**Git statusでローカルリポジトリの状態を見る**<br>
**git status**<br>
On branch master<br>
No commits yet<br>
Untracked files:<br>
(use "git add `<file>``..." to include in what will be committed)<br>
.DS_Store<br>
nothing added to commit but untracked files present (use "git add" to track)
- ## -🔴git add
### 🔵 $\textcolor{blue}{\text{2024/1/6}}$
ワークツリーに入っている編集済みのREADME.mdファイルを **git add** を実行して**ステージングエリアに登録する**。<br><br>
**git add README.md**<br>
On branch main<br>
No commits yet<br>
Changes to be committed:<br>
(use "git rm --cached `<file>``..." to unstage)
new file: README.md
- ## -🔴git commit
### 🔵 $\textcolor{blue}{\text{2024/1/6}}$
ステージングエリアに入っているREADME.mdファイルを **git commit** を実行して**Gitディレクトリに登録する**。<br><br>
**git commit**<br>
ここでVisual Studio Codeが開くので、コメントを入力し閉じる。<br>
Visual Studio Codeを閉じると、コミットが完了し、結果がTerminalに表示される。<br><br>
[main (root-commit) 6203a58] 第１回：READMEファイル作成<br>
1 file changed, 17 insertions(+)<br>
create mode 100644 README.md<br><br>
**Git statusでローカルリポジトリの状態を見る**<br>

**git status**<br>
On branch main<br>
Your branch is based on 'origin/main', but the upstream is gone.<br>
(use "git branch --unset-upstream" to fixup)<br>

nothing to commit, working tree clean<br>

#### 🔸🔸On branch main の branch とは？
Gitで記録する履歴を枝分かれさせるための機能で、同時に複数の異なる作業をしたい場合、内容ごとに別々に管理ができる。<br>
枝分かれしたブランチは任意のタイミングでマージできる。<br>
main は自動で作られたブランチの名称。
- ## -🔴git push
### 🔵 $\textcolor{blue}{\text{2024/1/6}}$
プッシュで変更内容をGithubのリモートリポジトリに反映する。<br>
git push の後ろにはブランチ名を指定したが$\textcolor{red}{\text{エラー}}$となった。<br>
**$\textcolor{red}{\text{git push main}}$**<br>
fatal: 'main' does not appear to be a git repository<br>
fatal: Could not read from remote repository.<br><br>
Please make sure you have the correct access rights<br>
and the repository exists.<br><br>
再度試みる。<br>
$\textcolor{blue}{\text{git push}}$ $\textcolor{green}{\text{origin}}$ $\textcolor{blue}{\text{main}}$<br>
が正しい。<br>
確かに、**$\textcolor{green}{\text{リモートリポジトリ自体の名称}}$** を指定する必要があった。<br><br>
Enumerating objects: 3, done.<br>
Counting objects: 100% (3/3), done.<br>
Delta compression using up to 8 threads<br>
Compressing objects: 100% (2/2), done.<br>
Writing objects: 100% (3/3), 1.94 KiB | 1.94 MiB/s, done.<br>
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0<br>
To github.com:MOyogi201710-MAU202401/mau-j2n.git<br>
`* [new branch] main -> main<br>
# -🔴githubアカウントの作成
### 🔵 $\textcolor{blue}{\text{2023/10/22}}$
GitHubのアカウントを決める際、個人情報のセキュリティを考慮し決め方についてネットで調べる。
- 自由に設定できる
- 半角英数字を使う
- 複数のGitアカウントを使いわけることができる
### 🔵 $\textcolor{blue}{\text{2024/1/4}}$
- GitHubにアカウント登録し **mau-j2n** リポジトリを作成する。
- SSHキーを作成する：タイトルはforMAU

正しくSSHキーを設定できたかを確認する。<br>
**ssh -T `git@github.com`**<br>
Hi MOyogi201710-MAU202401! You've successfully authenticated<br>
# -🔴githubへの公開方法
### 🔵 $\textcolor{blue}{\text{2023/11/19}}$
Visual Studio CodeでMarkdownファイルを作成する。<br>
現時点ではテスト用として　test_Markdown.md　を作成する。<br>
テストファイルでMarkdown構文をいろいろ試してみる。
### 🔵 $\textcolor{blue}{\text{2024/1/7}}$
ローカルPCで新規作成や修正したファイルをリモートリポジトリに反映できるようにする準備として、GitHubのリポジトリをローカルPCにクローンする。<br>
**git clone `git@github.com`:MOyogi201710-MAU202401/mau-j2n.git**<br><br>
ローカルPCにおいて作成しておいたREADME.mdをGitHubからクローンしたリポジトリに保存する（push）。<br><br>
リモートリポジトリの設定をローカルPCのTerminalから確認する。<br>
**git remote -v**<br>
origin `git@github.com`:MOyogi201710-MAU202401/mau-j2n.git (fetch)<br>
origin `git@github.com`:MOyogi201710-MAU202401/mau-j2n.git (push)<br>
「origin」はクローン元のリモートリポジトリを表す。<br>
教本によると、名称を変更することができる。<br>用途としては複数のリポジトリを扱う場合にそれぞれに名称を設定することとする。<br><br>
git statusで現状を確認する。<br>

On branch main<br>
No commits yet<br>
Untracked files:<br>
(use "git add `<file>``..." to include in what will be committed)<br>
README.md<br>
nothing added to commit but untracked files present (use "git add" to track)<br>

### 🔵 $\textcolor{blue}{\text{2024/1/8}}$
$\textcolor{red}{\text{Google Chromeのビューアーでは自動翻訳が起動し、日本語を日本語に翻訳してしまい意味のなさない文章になってしまうことに気づく。}}$<br>
インターネットで解決策を探す。<br>
以下の内、シンプルな方法`<code>` `</code>` で囲む方法にすることとする。
- https://qiita.com/ishiyama0530/items/8f8afc6c36ca8ea4df56<br>
- https://qiita.com/nkmr_jp/items/488a9a321ed938bf543f<br>
- https://penpen-dev.com/blog/translate-no-code/<br>

### 🔵 $\textcolor{blue}{\text{2024/1/13}}$
- 文字に色を設定する方法を探しHTMLの構文が使えるということで試す。
  - `<font color="色">`、`<span style="color: 色"></span>`　ともにChromeでもSafariでも有効にならない。
  - $\textcolor{red}{\text{Commitする際に記載するコメントもChromeでは日本語を別の日本語に翻訳してしまうため、要注意。}}$
  - 行間が広がりすぎるため、`<code>`も`<Pre>`も使わないこととした。
  - $\textcolor{red}{\text{文字の色を設定する方法を見つける}}$<br>
https://kanoe.studio/archives/1824/<br>
`<!-- ブラウザで名前が定義されている色名を指定する場合 -->`<br>
`$\textcolor{色}{\text{your text}}$`<br>
`<!-- 色コードを使用する場合 -->`<br>
`$\textcolor{１６新法表記}{\text{your text}}$`<br>

- 画像を表示する構文を調べ、表示したい箇所に画像表示の構文を設定する。
  - 画像ファイルをREANDME.mdファイルが入っているフォルダに保存する。
  - 構文`![alt用テキスト](相対パス付き画像ファイル名)`を設定する。

- プライベートからパブリックに変更し課題提出の準備をする。
