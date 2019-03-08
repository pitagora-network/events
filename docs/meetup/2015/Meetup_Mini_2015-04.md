---
title: Meetup Mini 2015-04
permalink: /Meetup_Mini_2015-04/
---

[Main Page](/Main_Page "wikilink") &gt;&gt; [Events](/Events "wikilink") &gt;&gt;

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

-   日時： 2015年04月23日（木）
-   場所： 先端研4号館4階セミナールーム
-   Skype ID：pitagora-network（[最新バージョン](http://www.skype.com/ja/)の使用を推奨）

|             |                                                      |
|-------------|------------------------------------------------------|
| 10:00-10:15 | 主旨のリマインド + 今日の作業確認                    |
| 10:15-10:30 | **ピ**タゴラギャラクシーの更新報告                   |
| 10:30-18:00 | **ピ**タゴラ装置の開発 （講堂接続確認：15:00-16:00） |
| 18:00-18:30 | 今日のまとめ + 次回の日程調整　**（Skype 参加可）**  |

内容
----

##### 前回振り返り

-   [Meetup 2015-04](/Meetup_2015-04 "wikilink")

##### 山中

-   VM 0.2.3 をリリースしました
-   会場の無線LANの設置作業

##### 大田

-   ワークショップでのトーク「データ取得ワークフロー by 大田」は「FANTOM5ワークフロー by 那須野さん」になりました
    -   内容について打ち合わせをしました。
    -   wikiにワークフローの情報を載せました <http://wiki.pitagora-galaxy.org/wiki/index.php/Workflow_CAGE_01>

<!-- -->

-   ハンズオンについて
    -   まず概要を説明する
        -   作ってる人たち
        -   できること
        -   どのように動いているか
    -   デモを動かしてもらう
        -   AWSのインスタンスを予めいくつか立てておいてそのURLにアクセスしてもらう
            -   ユーザ登録をしてもらう
            -   サンプルデータを読み込んでもらう
            -   ワークフローを流してもらう
    -   インストールをしてもらう
        -   Virtualboxのインストール
        -   ピタゴラのインストール
        -   起動してみる

<!-- -->

-   ワークショップの来場者アンケートつくってます
    -   聞いてみたいことがあれば教えてください

##### 加藤

-   各ワークフロー図の修正と作成（ChipSeq 03, Valliant Calling02, BS-Seq, Cage）

##### 芳村さん

-   発表スライドを作成
    -   チェックをお願いします &gt; オーガナイザーの皆様
    -   二階堂さんにも同時進行でチェックしてもらっております（一度見せているので、だいたいOKなはず）

##### 新海さん

-   ワークフローは載せないことになりました
-   発表スライドを作って頂いています！

##### 那須野さん

-   FANTOM5ワークフローの発表内容について大田さんと詰めました。私のほうでスライドを作成し、レビューしていただくことになっています。

##### 長崎さん

-   HLAツール移植用セット 準備しました。
-   Tool Shedで上げられるように今後用意。
-   ワークフロー図はもうチョイであげます。すみません。スライド準備し始めます。

##### 斎藤さん

-   宿題で BS-Seq 01 がほとんど完成
-   BS-Seq 01のWikiページに説明を追加
-   　BS-Seq 01のワークフロー図の下書きを作成
-   AWS での大規模テストに使うデータについて検討。前に自分の論文で使用した Breast cancer と Normal breast の WGBS データを SRX062003, SRX062004 にする予定。サイズはヒトゲノム 30--40X くらい。
-   commet　を大規模データへ適用するために必要なオプションを Galaxy の方では有効にしていなかったので、GUI から設定できるように tool を更新する必要がある。

参加者
------

-   山中（先端研）
-   大田（DBCLS）
-   加藤（理研IMS）
-   芳村さん（理研ACCC）
-   新海さん（産総研）
-   斎藤さん（産総研）
-   那須野さん
-   長崎さん（遺伝研）\*Skype
-   鈴木さん