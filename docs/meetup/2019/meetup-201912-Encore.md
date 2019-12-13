# Pitagora Meetup 2019-12 Encore

今回は [Kyushu Bioinformatics Community (KBC)](http://kyushubioinfo.mystrikingly.com/) との交流を目的とした福岡での開催です！

また、今回は [InterCloud-CREST](https://www.jst.go.jp/kisoken/crest/en/project/1111081/15655350.html) のサポートを受けています。InterCloud-CREST で開発している Academic InterCloud の技術開発に関するトーク「Academic InterCloud と CWL」をお願いしています。

## 概要

- 日時： 2019年12月12日（木）10:00 〜 17:00
- 場所： [みんなの貸会議室 天神西通り北店 803会議室](https://minnanospace.com/spaces/?tabId=under-20&room=803&utm_source=kaigisitsu&utm_campaign=803price) (福岡県福岡市)
  - 入り口が施錠されています。到着されましたら鍵を開けますので、以下の連絡先までご連絡ください。
- 連絡先：
  - 大田
    - Mail: t.ohta [at] dbcls.rois.ac.jp
    - Twitter: https://twitter.com/iNut
- Skype ID：pitagora-network ([最新バージョンのSkype](http://www.skype.com/ja/)の使用を推奨)

## タイムテーブル

途中参加、途中退出は自由です。ランチの時間は部屋に誰もいなくなる可能性があるので、施錠の関係上、この前後にお越し頂けるとスムーズです。

|Time||
|:---:|:---:|
|10:00-10:15|今日の作業確認|
|10:15-11:30|開発とディスカッション|
|11:30-12:30|ランチ|
|12:30-13:30|InterCloud presentation|
|13:30-16:30|開発とディスカッション|
|16:30-17:00|ラップアップ|
|17:00-|有識者会議|

## ミートアップの主旨

- データ解析ツール・ワークフローを共有する
  - ソフトウェアをコンテナ化する
  - Galaxy や CWL などを使ってツール定義、ワークフロー定義を書く
  - ドキュメントを書いて GitHub で公開する
- 共有されたツールやワークフローを実行する
  - うまくいったこと、うまくいかなかったことを記録する
- 技術情報を共有する
  - twitter に post する
  - ブログを書く
- 関連OSSプロジェクトにコミットする
  - SNSで質問する
    - hashtag をつけて twitter で
    - プロジェクトの Gitter channel があればそこで聞く
  - Issueを立てる
  - Pull Request を送る
- その他データ解析に関わる人々の日々の暮らしが豊かになる開発を進める

## まとめ

- 物理: 4人
- エア: 1人

### 大田

- DAT2-CWL のテストを通そうと頑張った
  - 通ってない
  - 多分 docker siblings のせいでコケてる
- 久保田さんが来てくれたのでCWLの紹介をした
  - 64秒の動画を見せた
  - 自分で書いたCWLを実行して見せた
  - 他の人のCWLファイルの[探し方](https://www.commonwl.org/#Repositories_of_CWL_Tools_and_Workflows)を紹介した
  - rabix composer でワークフローを作るやり方を見せた
- 久保田さんのラボの[ソフトウェア](http://www.bioreg.kyushu-u.ac.jp/labo/bioinfo/software.html)のうち PAL2NAL を Docker 化して CWL を書いた
  - 残念ながらライセンスが明記されていなかったのでコンテナイメージは公開してない、Dockerfileだけ
  - でもテストデータがあってexampleがちゃんとREADMEに書いてあったので最高に楽だった
  - 丹生さんの [template](https://qiita.com/tm_tn/items/3fafe22e2c4a92a7f597) を使って VSCode の remote container で開発した
  - [zatsu-cwl-generator](https://qiita.com/tm_tn/items/2c789c5b3c28e3eb3c9a)も使った
  - GitHub Actions で CI をやった、ローカルの Dockerfile をビルドするステップを突っ込んでゴリ押しでテストを通した


### 丹生
- CWL Live coding
    - 対象のツール: http://www.bork.embl.de/pal2nal/
    - 成果物: https://github.com/inutano/pal2nal-cwl
        - CI 用の `test.yml` や Github Actions の設定修正も含まれている
        - バッジが緑！
    - [CWL Advent Calendar](https://qiita.com/advent-calendar/2019/cwl) で紹介した[ツール](https://qiita.com/tm_tn/items/2c789c5b3c28e3eb3c9a)と[テンプレート](https://qiita.com/tm_tn/items/3fafe22e2c4a92a7f597)が早速役に立った
        - 素直なツールの場合、`zatsu-cwl-generator` を使うと一瞬で coding 部分が終わってしまう
- DAT2-cwl の担当最後のワークフローがもう少しで倒せそう
    - 暗黙に `.tbi` を生成するツールがあったため、後続ステップでエラーにならないと気づけない
    - 峠は超えた気がする

### 那須野
- Docker for Mac で Sibling Docker Container するのが難しいので、 [dind](https://hub.docker.com/_/docker) コンテナを使ってcwltoolを実行してみた (Sibling Docker in Docker)
  - 丹生さんがすでに VS Code の remote container を使った方法で記事を公開していた → [指先一つで立ち上げる CWL ツール・ワークフロー作成環境](https://qiita.com/tm_tn/items/3fafe22e2c4a92a7f597)
      - ユーザビリティ観点でも VS Code remote container のほうがわかりやすいですね！

実行手順メモ：
1. Docker for Mac で dind コンテナを起動＆接続
```
docker run --privileged -tid --name dind -v $(pwd):/mnt docker:19.03.5-dind
docker exec -ti dind sh
```
2. [雑に始める CWL！](https://qiita.com/tm_tn/items/4956f5ca523f7f49f386) の CWL を実行してみる。
```
/mnt # ls -l /usr/local/bin/ > lshead.txt

/mnt # cat <<EOF > ./cwltool
#!/bin/sh
docker run -v /var/run/docker.sock:/var/run/docker.sock -v /tmp:/tmp -v "\$PWD":"\$PWD" -w="\$PWD" commonworkflowlanguage/cwltool "\$@"
EOF

/mnt # vi head.cwl
cwlVersion: v1.0
class: CommandLineTool
baseCommand: [head]
arguments: [-n$(inputs.nlines), $(inputs.source)]
inputs:
  - id: source
    type: File
  - id: nlines
    type: int
outputs:
  - id: out
    type: stdout
requirements:
  - class: DockerRequirement
    dockerPull: debian:latest
EOF
```
3. cwltool (in dind コンテナ) 実行
```
/mnt # sh cwltool head.cwl --source lshead.txt --nlines 5
INFO /usr/local/bin/cwltool 1.0.20191206125148
INFO Resolved 'head.cwl' to 'file:///mnt/head.cwl'
INFO [job head.cwl] /tmp/qr1slmyu$ head \
    -n5 \
    /tmp/tmptf3bww_t/stgd9587d76-007b-4df9-87fa-06d8ebc692cf/lshead.txt > /tmp/qr1slmyu/0328c0c0e60bf6e0814e864edabec6d89c309ecf
INFO [job head.cwl] completed success
{
    "out": {
        "location": "file:///mnt/0328c0c0e60bf6e0814e864edabec6d89c309ecf",
        "basename": "0328c0c0e60bf6e0814e864edabec6d89c309ecf",
        "class": "File",
        "checksum": "sha1$69e6fcad4c097dcbde1f91d4b87de9c81b967024",
        "size": 277,
        "path": "/mnt/0328c0c0e60bf6e0814e864edabec6d89c309ecf"
    }
}
INFO Final process status is success
```

- [Galaxy Stable 19.05](https://github.com/bgruening/docker-galaxy-stable/blob/master/galaxy/Dockerfile) では、ベースイメージとして [toolshed/requirements](https://hub.docker.com/r/toolshed/requirements) を使わないようになったことを確認。
    - ubuntu:18.04 を使用
    - イメージサイズが少し小さくなった。(↓変遷)
```
~$ docker images|grep bgruening
bgruening/galaxy-stable:19.05.1  1.78GB
bgruening/galaxy-stable:19.01    3.77GB
bgruening/galaxy-stable:18.05    3.46GB
bgruening/galaxy-stable:17.09    2.1GB
```

→ 普通に起動できることを確認

```
docker run -d -p 8080:80 -p 8021:21 -p 8022:22 bgruening/galaxy-stable
```

```
(base) root@56eb7982898a:/galaxy-central# supervisorctl status
autofs                           FATAL     Exited too quickly (process log may have details)
condor                           RUNNING   pid 630, uptime 0:00:09
cron                             RUNNING   pid 487, uptime 0:00:40
docker                           STOPPED   Not started
galaxy:galaxy_nodejs_proxy       RUNNING   pid 613, uptime 0:00:14
galaxy:galaxy_web                RUNNING   pid 136, uptime 0:00:55
galaxy:handler0                  RUNNING   pid 137, uptime 0:00:55
galaxy:handler1                  RUNNING   pid 138, uptime 0:00:55
nginx                            RUNNING   pid 133, uptime 0:00:55
postgresql                       RUNNING   pid 456, uptime 0:00:50
proftpd                          RUNNING   pid 499, uptime 0:00:38
rabbitmq                         RUNNING   pid 134, uptime 0:00:55
reports                          RUNNING   pid 505, uptime 0:00:36
```

### 久保田

- はじめまして
- CWLについてよく知らなかった
- が，大体のイメージは掴めた（気がする）
    - [丹生さんの記事](https://qiita.com/tm_tn/items/4956f5ca523f7f49f386)をみながらひとまず動かしてみよう
- そもそも「こんてな？どっかー？？」状態である
- Rabix Composerはすぐに使えるようになりたい！


### 池田
- Galaxy Release v19.09が出たよ その2
	-画像への注釈ツールの使い方 (途中)
