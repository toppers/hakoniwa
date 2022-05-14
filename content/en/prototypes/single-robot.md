+++
description = "マイコンシミュレータと箱庭の連携事例"
bref = "マイコンシミュレータと箱庭の連携事例"
title = "マイコン制御ロボットシミュレーション"
draft = false
weight = 100
toc = true
script = 'animation'
images = ["img/prototypes/modelAdemo1.gif"]
github =  "https://github.com/toppers/hakoniwa-single_robot"
+++

単体のSBCで構成される単体ロボットを対象とした箱庭プロトタイプモデルです．[ETロボコン](https://www.etrobo.jp/)を題材としています．  
組込みマイコン上のプログラムの振る舞いを，ロボット上の挙動と連携させて検証を進めることができます．

### 技術研鑽視点での狙い

- 物理シミュレータとマイコンシミュレータ間の連携方法の検討
- 異なるシミュレータ間の時間同期の検討

### その他の狙い

- ETロボコンユーザ層に箱庭を広める（広報活動）

{{< image src="/img/prototypes/modelA.png" width="700" >}}

### 導入方法と使用方法

最小の構成と手順で単体ロボット向けシミュレータを試行できるパッケージを，下記のGitHubリポジトリで公開しています．ぜひ試してみてください．

- [toppers/hakoniwa-single_robot: 箱庭プロトタイプモデルA：単体ロボット向けシミュレータ](https://github.com/toppers/hakoniwa-single_robot)

### 動作例のデモ

![modelAdemo](/hakoniwa/img/prototypes/modelAdemo.gif)

![modelAdemo1](/hakoniwa/img/prototypes/modelAdemo1.gif)

![modelAdemo2](/hakoniwa/img/prototypes/modelAdemo2.gif)

---

#### 謝辞・特記事項：

Unityパッケージの設計と作成にあたっては，宝塚大学 東京メディア芸術学部 吉岡章夫准教授および学部生の杉﨑涼志さん，木村明美さん，千葉純平さんにご協力いただきました．

HackEVのUnityアセットは，ETロボコン実行委員会より提供いただいたデータを基に作成しています．実行委員会の皆さまに深く感謝いたします．  
ただし本アセットはETロボコンの本番環境とは異なりますので，大会に参加予定の方はご注意ください．また，本アセットは，個人利用または教育利用に限定してご利用ください．
