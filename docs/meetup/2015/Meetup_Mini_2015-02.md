主旨
----

1.  ツールやワークフローを持ち寄って、次のバージョンのImageに加える [（図）](http://www.pitagora-galaxy.org/_/rsrc/1416890873801/about/about_overview.png)
    -   実際には、加えるための手順を作って、Imageの管理者と共有する
    -   同時に、Wikiに加えるツールやワークフローの説明を記載する
2.  プロジェクトを改善するためのフィードバックを収集する
    -   解析プラットフォーム管理に役立つ技術ネタを共有する
    -   Galaxy以外のソフトウェアを扱っていく可能性について議論する

スケジュール
------------

-   日時： 2015年02月26日（木）
-   場所： アマゾン データ サービス ジャパン株式会社　会議室 [（地図）](https://s3-ap-northeast-1.amazonaws.com/adsj-office/ADSJ-MAP.pdf)

|             |                               |
|-------------|-------------------------------|
| 10:00-17:00 | **ピ**タゴラ装置の開発        |
| 17:00-17:30 | 今日のまとめ + 次回の日程調整 |
| 17:30-18:30 | 残作業など                    |

内容
----

-   [前回振り返り](/Meetup_2015-02#.E5.86.85.E5.AE.B9 "wikilink")
    -   3月5日勉強会でピタゴラ使う（大田）&gt;&gt; 資料ください
    -   VMWare Fusionで動かす手順作成 修正（池田) 前回の手順に加えて &gt;&gt; 手順 アップお願いします！
    -   データをホストしてくれませんか？（山中）DBCLS？遺伝研？情報研？訊いてみてください（大田）
    -   情報研の人に来ていただきましょう！（大田）
        -   声をかけて、興味をもって頂けましたが今回は日程合わずでした。
        -   関係する開発会社の方とかも合わせて、次回お誘いします。
    -   Revision と Version のヒモ付 Revision レベルで Reproducibility が必要なのでは？
        -   [ここ](https://docs.google.com/spreadsheets/d/1oECYODffa-Anrms50-Ktrz6w9RnsAoy5IUcgK7Ysd5Y)にまとめることにしました

##### 山中

-   4月のワークショップの告知どうするか、Twitterハッシュタグどうするか
    -   ML: 2回（予告と詳細）送る。Bioinformatics-JP、NGS現場の会、CBI交渉（山中）
-   ワークフローの管理方法検討。Tool Shed で管理する際、Repository/Tool Dependency はどうやってつけるか。そもそも必要か（w/ 大田さん）
    -   ワークフローは Test Tool Shed の pitagora-workflows に集約する。現時点では Dependency は付けず、スプレッドシート（上記）で管理している。
-   Variant Calling のワークフローに必要なツール一覧の作成（w/ 池田さん 新海さん）
-   ライセンスのある GATK をインストールする方法（w/ 池田さん）
-   SRA から Galaxy にファイルをダウンロードする方法をまとめる（w/ 大田さん）
    -   FASTQ が欲しい場合： DDBJ に FASTQ があればリンク取得＆ペーストでダウンロード、しかし DDBJ は新しい FASTQ 変換を停止している
    -   そのため、SRA &gt; FASTQ のツールを入れる必要あり。Tool Shed の fastqdump ツールを試してみる（大田さん）
    -   DBCLS SRA を Galaxy 外部ツール化できるとさらにいい（大田さん）
    -   Workshop にて「データをどうやって取ってくるか」をひとつのセッションとして大田さんに話してもらうか
-   Workshop の話の流れを PPT テンプレートで作る（w/ 加藤さん）
    -   自己紹介 &gt; どのように Galaxy を使っているか &gt; ここで扱う解析の内容 &gt; 一般的な解析方法 &gt; 公開したワークフローの紹介
-   Workshop のポスター簡易版を完成させる、Registration Open する（w/ 加藤さん）
    -   皆様、[こちら](https://docs.google.com/forms/d/1ptS9Dk8BWyzcCVxpOyzSo_S78HxsYuD8WSLhR609Od4/viewform)から登録お願いします。
-   残タスク
    -   ユーザーがどのワークフローorツールをどれだけ使ったか集計する方法は？（w/ 仲木さん）
    -   Proxy 設定の問題解消（ModRewrite 設定、設定している人がいれば訊きたい）
    -   ゲノム解析に詳しくない人（例えば、HPCのProvider）でも楽しめるワークフローを作れるか
    -   Galaxy の FTP 機能の有効化（ProFTPD を使う）[Galaxy Wiki](https://wiki.galaxyproject.org/Admin/Config/UploadviaFTP?action=show&redirect=Admin%2FConfig%2FUpload+via+FTP)
    -   GCC2015 Abstract Submission 皆さんに相談
    -   手動ならばうまくいくのに API 経由だと dependency のインストールが cloning で止まってしまうツール（macs14, tophat2）の問題解決

##### 大田

-   本日夜のApache Mesos勉強会でPitagoraの宣伝するためにスライドつくる
    -   スライドできた。ワークショップの告知を入れました
    -   バイオ関係ない開発者の人でも興味を持って来てくれるといいな〜と思っています
    -   のちほど speakerdeck.com/inutano に上げます
-   来週木曜のDB講習会@東京農工大でPitagoraの講習するための資料の準備
    -   進捗だめです
-   FANTOM5 CAGE workflowをgalaxyに載せる
    -   情報研の方と協働でやっています
    -   workflow再現のための情報をFANTOMのチームの人に訊く
        -   訊く前にコードを読む
            -   RのコードがUGEバックエンドありの環境とそうでない環境用がある
            -   UGEバックエンドなしなら動かせるかも
-   GCC2015の内容を考える
    -   そもそも行けるかどうかはセンター長判断次第なので現時点では未定
    -   山中さんがピタゴラの話をするので情報研とやってる話とかreproducibility as a serviceの話と絡めたい
    -   口頭でsubmitしたい
    -   4/10にtalk abstract submissionがcloseする
    -   key dates <http://gcc2015.tsl.ac.uk/key-dates/>

##### 芳村

-   SailfishWFの残作業を確認する（→山中さん）
-   残作業をリストアップして優先順位付け
-   SailfishWFのセットアップ手順、必要なツール一覧をドキュメント化？
-   Galaxy仮想環境のプロビジョニング関連ツールの修正
-   理研の運用するGalaxyで上がっている課題を相談したい
    -   API_KEY, fastqのインポート方法など
-   ▶本日の進捗
-   Sailfish WFのフロー図
    -   加藤さんが作図してくれた
-   使い方のドキュメント（Wikiに書く）について
    -   必要だが、公開前にできれば良い
    -   [http://wiki.pitagora-galaxy.org/wiki/index.php/Workflow_RNA-seq_01みたいなイメージ](http://wiki.pitagora-galaxy.org/wiki/index.php/Workflow_RNA-seq_01みたいなイメージ)
    -   書けそうなら業務の合間に進めておく
-   中岡さんとRNA-seqWF発表内容のすり合わせ
    -   DEGのところは実験デザインによってインプットが多様なので軽くする、定量→DEG→高次解析 とつなぐ
-   ▶Todo
    -   Galaxy環境にSailfish indexを作成し、locファイルを作成
    -   プロビジョニング検討の段階に相談する
    -   自動構築ツールは理研用のがすでにgithubにある
-   ToolShedに修正したSailfishツールをコミットする
    -   gitと同じように、リポジトリを作ってからソースコードをaddしてpushする

##### 加藤

-   芳村さんのWorkflow図作成
-   <http://wiki.pitagora-galaxy.org/wiki/index.php/Workflow_RNA-seq_02>
-   ツール一覧ページ修正
    -   <http://wiki.pitagora-galaxy.org/wiki/index.php/Tools>
-   ポスター簡易版
    -   [10px](/File:WST2015_C2.png "wikilink")

##### 中岡

-   はじめてなので議論に参加する。
-   4月発表予定の RNAseq pipeline の続き作成
-   ▶本日の進捗
    -   理研内 cloud の件で芳村さんと打ち合わせ、Pitagora への反映も含めて基本的方針を話し合って決定
    -   4月発表 RNAseq の件で芳村さんと発表内容について相互確認。芳村さん→中岡という順番で話すにあたって、連携も含めた発表内容を決定 (SailfishWF -&gt; edgeR などを介した DEG -&gt; \*\*\* DEG で選定した遺伝子から GO や PPI や visualization といった基本処理)
    -   Tool Shed リポジトリの作成
    -   最新バージョンでの動作確認
-   ▶Todo
    -   IMS の既存 NGS パイプラインの Galaxy への反映については、3/6 山中さんと IMS 内で話し合い
    -   Tool Shed リポジトリに登録する script の完成
    -   4月発表時に利用するデータセットとデモの準備

##### 池田

-   Variant call ツールの提供
    -   GATK 3.3 で動くようになった。リファレンスをどうするのか等の部分でPending。
    -   ツール作成の手順をまとめる（[ツールの開発](/ツールの開発 "wikilink")）
-   Pitagora-Galaxy 0.1.7 をVMware Fusionで動作させる
    -   OVA はすぐに動いたが、eth0/1 の設定スクリプトを使って Fusion で動かせる
-   GATK on Pitagora-Galaxy?

##### 斎藤

-   BisulfighterのGalaxyへの移植について考えた
-   リードマッピングのツールbsf-call、メチル化変化領域検出のツールComMet
-   Bisulfighterは2つのパッケージからなるワークフローとして実装する予定

##### 仲木

-   エピゲノム解析用ワークフローのラッパーの作成 (by xml)
    -   Ryo's gadgetsのツール1つについて、ローカル環境のPitagora-galaxy上で動作することを確認した。
    -   (To do) 次回は、その他のツールについてもラッパーを作成すると共に、簡単な説明文をつける。
-   エピゲノム解析用ワークフローのサーバーサイドプログラムの作成 (by java)
    -   その他のRyo's gadgetsツールを一括で管理するjarファイルを作成した。
    -   (To do) 次回は、その他のツールについてもjarファイルに追加する。

##### 吉荒さん

-   AWS 初心者向け、AWS でアカウント作成から Pitagora 起動までのイントロ

参加者
------

-   山中（先端研）
-   大田（DBCLS）
-   加藤（理研IMS）
-   吉荒さん（Amazon）
-   芳村さん（理研ACCC）
-   仲木さん（先端研）
-   新海さん（産総研）
-   斎藤さん（産総研）
-   池田さん（Percipere）
-   中岡さん（理研IMS）
-   Nikosさん（SBI）
-   長崎さん（遺伝研）
