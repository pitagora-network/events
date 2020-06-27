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

-   日時： 2015年03月26日（木）
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

-   [Meetup 2015-03](/Meetup_2015-03#.E5.86.85.E5.AE.B9 "wikilink")

##### 山中

-   Variant Calling（w/ 新海さん）
    -   ワークフロー化する部分を決定 [Admin Variant Calling 01](/Admin_Variant_Calling_01 "wikilink")
    -   これからやること
        -   いただいた Wrapper を Tool Shed に登録
        -   GATK を取ってきて、いただいた Wrapper を動作確認
        -   GATK を取ってくる Dependency Package を作る？
        -   テストデータを新海さんに用意してもらう
-   Sailfish（w/ 芳村さん）
    -   Sailfish の Dependency をつくった [Admin RNA-seq 02](/Admin_RNA-seq_02 "wikilink")
    -   これからやること
        -   芳村さんの Wrapper に Dependency Package を参照させる
        -   芳村さんの Wrapper を Tool Shed に登録
        -   芳村さんの Workflow を動作確認
        -   テストデータを芳村さんに用意してもらう
-   ChIP-seq（w/ 仲木さん）
    -   Sicer をインストール、動作未確認、[これ](https://biostar.usegalaxy.org/p/3710/)に従ってやる
    -   モチーフロゴを表示する JavaScript いつか作れたら嬉しい

##### 中岡

-   前回から現在まで: 公共データから時系列 FASTQ データを取得して Tophat/bowtie2 で bam を作成
-   前回から現在まで: bam2readcount | edgeR | enrichment / PPI / heatmap / time-course plot visualization のあたりの script を連動させ、実際に Galaxy 上で動くことを確認する作業を行った。
    -   read count ファイル群をアップロードして、zip に固めて処理する方針にしている。その script を除いて、全て完成して動作確認を行った。
    -   加藤さんに workflow の作成をして頂いた。
-   Galaxy とは少々話がずれるが、理研 IMS で、RNA-seq/ChIP-seq 用 webpage (RefDIC) 開発者である土方さん、当時のラボボスの小原先生に RefDIC 仕様の公開は OK であるという了承をもらったので、芳村さんとお話したときに RIKEN 和光の cloud でもし活用・参考にして頂く分には問題ないということになった。

<!-- -->

-   今後やること: workflow の解説を記載、Tool dependencies の記載 (個人用 Evernote に書いているので、基本はその記事を転用する)、パワーポイントプレゼンテーション資料の作成、ToolShed repository を介した software の登録

##### 加藤

-   wikiのTopページのダウンロードアイコン変更
-   ワークフロー図関連
    -   レイアウト：幅は800px固定、２段組にして、左にテキスト、右にフロー図（幅400px)で変更していく（作業中）
    -   メタ情報については、各ワークフロー図作成後に修正して掲載。現段階では削除。
    -   長崎さんに情報提供のご依頼
    -   芳村さんにページ更新依頼
-   講堂レイアウトの確認（配置図案作成）
-   初期登録者に懇親会の参加確認メール

##### 新海

-   今後の作業内容について情報交換と確認
-   まずは調達版galaxyをきちんと動かせるよう調整を続ける

##### 長崎

<https://p-galaxy.ddbj.nig.ac.jp/workflow/list_published> のHLA2 Workflow (alpha)
途中終了のバグとれてるかチェック中。
テスト用データ場所&gt;&gt; <https://sites.google.com/a/g.nig.ac.jp/p-galaxy-help/home/howto/hosomichi-hla-analysis-tools#TOC-K-0328_S66_L001_R1_001.fastq-forward-and-K-0328_S66_L001_R2_001.fastq-reverse->

参加者
------

-   山中（先端研）
-   加藤（理研IMS）
-   新海さん（産総研）
-   中岡さん（理研IMS）
-   長崎さん（遺伝研）
-   仲木さん（先端研）
