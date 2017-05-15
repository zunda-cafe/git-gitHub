==================================
はじめに
==================================


教材
==================
* GitHub実践入門
    * https://www.amazon.co.jp/GitHub実践入門-~Pull-Requestによる開発の変革-PRESS-plus/dp/477416366X?SubscriptionId=AKIAJ5QYOHUBLNKYFZHA&tag=hirocaster-22&linkCode=xm2&camp=2025&creative=165953&creativeASIN=477416366X

* kazuのまとめ
    * http:///bookinfo.wiki.fc2.com




==================================
GitHub実践入門
==================================

1. GitHubの世界へようこそ
====================================================
- GitHubはGitHub社で提供されるGitリポジトリのホスティングサービス
- Gitはリポジトリだけ、GitHubはGitリポジトリ+WebUI+便利な機能いろいろ
- Gitを使うことで、コラボレーションの形が変わる
    - PullRequestで自分が変更したソースを、元の開発者に取り込んでもらえる
    - @ユーザ名によるNotificationsをつけると気づいてもらえる
    - GitHub Flavored Markdown(GFM)という気泡であらゆるものを記述可能
    - 気にあるリポジトリをWatchしておけばNewsFeedに流れてくる
    - 世界中が同じ開発スタイルになる

- ソーシャルコーディング
    - 世界を閉ざさず、多種多様な文化を見る
    - 本当にコードが書ける人が求められている
        - 人間性やマネジメント能力よりも
    - 他人が書いたコードを簡単に見れる
    - 自分が書いたコードを簡単に公開できる
- GitHubの主な機能
    - Gitリポジトリ
        - 基本的にオープンだが、定額払えばprivateも可能
    - Oganization
        - アカウントや権限を統一することが可能
    - Issue(task/issue管理)
	- トラッキングや管理ができる機能
    - wiki
        - GFMで記述できるwikiが使える
    - Pull Request
      　- 機能追加やバグフィックスを本家に取り込んでもらうためのリクエスト

2. Gitの導入
====================================================
- ソースコードの変更履歴を管理すること
    - Subversionは集中型
        - リポジトリは一つ
    - Gitは分散型
        - リポジトリが複数、fork/PullRequestでリポジトリ間のやりとりをする
    - 集中型の方が簡単だが、分散型でも集中型と同じ使い方ができるので、Gitがおすすめ

- linux,macはデフォルト絵インストールされている
- windowsはmsysGitなどを使う

3. GitHubを利用する準備
====================================================
- GitHubのアカウントを作成する
- https://github.com/join
- SSHの鍵を設定することもできる

- ユーザ名の横の＋マークでnew Repositoryで新しいリポジトリを作る

4. Gitを操作しながら学ぶ
====================================================

基本的な操作
-------------

- git init
    - リポジトリの初期化
    - bareオプションでワーキングディレクトリを持つかを指定

- git status
    - リポジトリの状態の確認
    - 不具合が起きた時などによく使う

- git add
    - ステージ領域(インデックス)に追加
    - 編集後も一度addしてからコミットする

- git commit
    - コミットをして変更を記録する
    - git commit -m "message"でメッセージを付けられる

- git log
    - ログの確認
    - ファイル名/ディレクトリ名/深さを与えると対象を指定できる
        - graphオプションでブランチを視覚的に表示する
	- オプションがいろいろあるし、フィルタもできる

- git diff
    - ワーキングツリー/ステージ領域/最新コミット間の差分を表示する
    - 二つのファイルを明示する
    - git diff HEAD でワーキングツリーと最新コミットの差分を表示

ブランチ操作
-------------
- git branch
    - ブランチの一覧を表示する
    - 現在のブランチには*が表示される
    - git branch ブランチ名で新しいブランチを作成する

- git checkout ブランチ名
    - ブランチに切り替える
    - git checkout -で前のブランチに切り替える
    - git checkout -b ブランチ名でブランチの作成と切り替えを同時に行う

- git merge ブランチ名
    - マージ先で作業を行う
    - マージ先から、マージしたいブランチを呼び込む

- git reset
    - 歴史をさかのぼる 
    - 過去のある時点からブランチを作成したいときに使う
        - git reset --hard {hash}
  	- hashのコミットにローカルのファイル状態を含めて戻す
- git rebase -i
    - 歴史を押しつぶして改変
    - スペルミスなど簡易修正のために歴史をつぶして改変するときにつかう

リモートリポジトリへの送信
--------------------------

- git remote add
    - githubなどでつくったリポジトリを登録する

- git push 
    - git remote addで作ったリモートリポジトリへ送信する

- git clone
    - リモートリポジトリから情報を取得する

- git pull
    - 最新のリモートブランチを取得する


5. GitHubの機能を徹底解説
====================================================
教科書とUIが少し変わっているので、新しい画面と合わせて説明

- ショートカットキー
    - いろいろあるので覚えると便利
    - 画面でShift+/で一覧が表示される

- ツールバー
    - ロゴ
        - ダッシュボードに戻れる
    - Notifications
        - すずのマークで変更や通知を確認できる
   	- メールへの送信設定もできる
    - 検索ウィンドウ
      　- ユーザやコードの断片でも検索してくれる
    - Gist
        - リポジトリに入れるほどでもないコードを管理後悔するために使う
	- 構成管理され変更履歴の管理やforkもできる
    - Create a new ...(+マーク0
        - 新しいリポジトリやOrganizationの作成
    - Account Sttings
        - アカウントの設定をいろいろいじれる

- ダッシュボード
    - New Feed
        - FollowユーザやWatchしているプロジェクトの活動状況が流れている
    - PullRequest
        - 行ったPullRequestやその後どうなったかを追える
    - Issues
        - リポジトリやアサインされたissueを確認できる

- プロフィール
    - ユーザ情報
        - 名前や所属、メールアドレス、organizationなど
        - ここでfollowをするとNewsFeedい活動が流れてくる
    - Repositories
        - ユーザが公開しているリポジトリが表示される
        - 人気がstarで表示される

- リポジトリ
    - code
        - リポジトリに入っているファイル一覧を表示
    - issues
        - バグや機能追加などを管理
    - PullRequest
        - PullRequestを管理
    - Wiki
        - wikiで情報を管理できる
    - pulse
        - リポジトリの活動情報を表示
    - Graphs
        - リポジトリの活動指標をグラフで表している
    - Settings
        - リポジトリの設定を変更
    - commits
        - commit/commit数
    - branches
        - ブランチの一覧/ブランチ数
    - releases
        - タグ一覧が表示
    - contributors
        - リポジトリに対してコミットしたプログラマの一覧

差分の閲覧
-------------
- URLを直接指定すると差分がみれる
    - Ruby on Railesのブランチ差分の例
        - https://github.com/rails/rails/compare/4-0-stable...3-2-stable
    - Ruby on Railesの数日前の差分の例
        - https://github.com/rails/rails/compare/master@{7.day.ago...master}


Issue
-------------
- バグトラッキングを管理できる(チケット管理)
    - issue及びコメントはGFMで記述できるため、表現力が豊か
    - シンタックスハイライトもできる
- issueにはラベルをつけられたり、マイルストーン管理が可能
- タスクリスト記法が使える
    - [x]でかくとチェックボックスになる
- コミットに特定のフォーマットの記述を書くことでissueの操作ができる
    - issueをクローズする例
        - fix #1
	- fixes #2
	- fixed #3
	- close #4
	- closes #5
	- closed #6
	- resolve #7
	- resolves #8
	- resolved #9
- issueをPullRequestに変換
    - issueとPullRequestの番号は共通なのでGitHubのAPIで変換が可能


PullRequest
-------------
オープンになっているPullRequestの詳細を確認できる

- Conversion
    - PullRequestに関するコメントやコミット履歴を確認できる
- commits
    - PullRequestに関するコミットの一覧が時系列で確認できる
- Files Changed
    - PullRequestに関して変更されたファイル内容と差分が確認できる


Wiki
-------------
単純な記法でドキュメントを作成、編集できる機能

- Pages
    - ページの一覧

- History
    - wikiの変更履歴を確認できる

Pulse
-------------
- active pull requests
    - 期間内に行われたPullRequestの数やマージされた数が表示される

- active issues
    - 期間内に行われたissueが表示される


6. はじめてのPullRequest
====================================================
- PullRequestとは
    - あなたが加えた変更を相手のリポジトリに取り込んで欲しい時に使うもの

- どんな時に使うか
    - 便利なソフトウェアを利用していた
    - 使っているうちにバグを見つけて、修正して使っていた
    - 本家に反映してもらえば、他の人の役にたつ
    - PullRequestを送れば、貢献者となりみんなの役にたつ

- PullRequestの準備
    - オリジナルをForkして自分のリポジトリを作成する
    - ローカルにcloneする
    - トピックブランチを作成する
    - コードを修正する
    - 変更をコミット
    - リモートブランチの作成
    - PullRequestを送る


- 開発途中に議論をするためにPullRequestを送るという手法もある

- ForkせずにブランチからPullRequestを送ることも可能
    - リポジトリへの書き込み権限があれば、トピックブランチを作成しPullRequestを統合ブランチに送ることができる

7. PullRequestが送られてきたら
====================================================
- PullRequestが送られてきたら、一覧に表示される
- まず、ソースコードレビューをする
    - ソースだけでなく、画像の差分なども確認できる
- 次に、PullRequestを送ってきた人のリポジトリをクローンする
- 確認用のブランチを作成し、PullRequestの内容をマージする
- 問題がなければ、PullRequestをマージする


8. GitHubと連携するツールとサービス
====================================================
- hubコマンド
    - gitコマンドをさらに使いやすくしたもの

- Travis CI
    - CIツール、TravisCIに接続して連携設定をする

- Jenkins
    - CIツール、多機能で様々なことができる

- Coveralls
    - カバレッジツール
    - TravisCI/Jenkinsなどが稼働していればすぐに使える

- Gemnasium
    - 最新のソフトウェア/ライブラリがリリースされていないかなどを確認できる


9. GitHubを利用した開発フロー
====================================================
- 全てをシンプルにすること
    - 本当に全部の機能やルールが必要なのかを考える
    - GitHubだけで必要な機能はほぼ全てある
        - 他の機能と連携する場合、本当にそれが必要なのか考えてから入れる

- リポジトリをforkしないで使う方がよい
    - リポジトリは1つで各々がpush/pull/PullRequestをするのが簡単

- 常にデプロイ。リリースという概念はない
    #. masterブランチは常にデプロイ可能な状態とすrう
    #. 新しい作業をするときは、masterからブランチを作成する
    #. 作成したローカルリポジトリのブランチにコミットする
    #. 同盟のブランチをGitHubのリポジトリに作成し、定期的にpushする
    #. 助けやフィードバックが欲しい場合は、PullRequestを出す
        - ブランチをmasterにマージする時以外にもPullRequestを活用する
    #. 他の開発者がレビューをして、完了したらmasterにマージ
    #. masterは直ちにデプロイ
        - デプロイは必ず完全自動化する

- 具体的な例
    #. git clone https://XXX.git
    #. git checkout -b topic_branch
    #. git push -u origin topic_branch
        - 他の人にブランチ作成と作業を通知するため
    #. 新機能実装
    #. テストコード作成
    #. PullRequest作成
    #. フィードバックを受ける
    #. PullRequestを育てる(フィードバックを反映する)
    #. PullRequestがマージされる

- GitHubFlowをチームで実践するために
    - PullRequestのサイズを小さくする
        - 1つの機能を1つのブランチとすると大きすぎる
    - 試せる環境を作ること
    - PullRequestへのフィードバックを多くしすぎない
        - なかなかマージされずいつまでもクローズされない
        - コミュニケーション不足なら話し合いの場を持つ方が早い
        - 技術力不足なら、ルールの整備、勉強会、ペアプログラミングなどを実施する

Git Flow
-------------
- 理解しやすい標準的な流れ
    #. 開発用のブランチ(develop)から作業用のブランチ(future branches)を作成する
    #. 作業用ブランチでの修正が終了すると、開発用ブランチに取り込まれる
    #. 上記を繰り返しリリースできるレベルまで機能を育てたら、masterに統合され、タグを打ってリリースされる
    #. リリースしたものにバグがあれば、hotfixesをタグから作成し作業する

- ワークフローも可能な限り簡単にすること

- 具体的な例
    - ブランチは以下のとおり
        - master 常にリリース可能なブランチ。直接コミットはしない
        - develop 開発中の中心となるブランチ。直接コミットしない
	- feature developから作成され、直接コミットして編集するブランチ
        - release developから作成され、リリース準備のために行うブランチで、メタ情報の更新や最終試験などのバグフィックスを行う。このブランチで仕様変更や機能追加などをしてはならない

    #. developからfeatureブランチを作成する
    #. featureブランチで機能を実装する
    #. GitHubを通じて、developブランチへPullRequestを送る
    #. 他の開発者のレビューを受けて、developにマージする 
    #. developブランチからreleaseブランチを作成し、最終試験が行う
    #. releaseブランチをmasterブランチにマージしタグを作成する
    #. バグやセキュリティ脆弱性を見つけたら、hotfixブランチをmasterから作成する
    #. 修正が終われば、masterと(開発中なら)developにPullRequestを発行し、マージする



10. 会社でGitHubを使おう
====================================================
- organizationを使う
- セキュリティ要件を確認する
- メンテナンス時間を確認する
- 障害情報を確認する
- オンプレミス版のGitHub Enterpriseを検討する
- Gitホスティングの別のサービスを検討する
    - GitBucket
    - GitLab
    - Gitorious
    - RhodeCode


AppendixA. GitHubをサポートするGUIクライアント
====================================================
- GitHub for Mac/GitHub for windows
    - GitHubからのクローン
    - リポジトリの歴史を表示
    - リポジトリの変更内容をコミット
    - ブランチの切り替え
    - GitHubへのpush
    - 通知センターへの通知(macのみ)
    - GitHubEnterpriseとの連携(macのみ)

- SourceTree
    - Git/Mercurialに対応
    - Git-flowをサポートしている


AppendixB. Gistで手軽にコード共有
====================================================
手軽にソースコードを公開できる

- Gist description(省略可)
    - ファイル群の説明文を記載

- filename(省略可)
    - ファイル名を指定

- add file
    - ファイルを追加したい場合


- Create secret gist/Create public gist
    - gistの作成


- 閲覧してコメントも残せる

そのほか
====================================================
- コマンドの練習になったサイト
    - http://pcottle.github.io/leaarnGitBranching/

- Macの通知センターでGitHubで受け取れる


.. toctree::
..   :maxdepth: 2
..   :caption: Contents:

.. * :ref:`genindex`
.. * :ref:`modindex`
.. * :ref:`search`
