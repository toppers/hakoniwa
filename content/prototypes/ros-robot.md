
+++
description = "ROSと箱庭の連携シミュレーション例"
bref = "ROSと箱庭の連携シミュレーション例"
title = "ROS制御ロボットシミュレーション"
draft = false
weight = 200
toc = true
script = 'animation'
images = ["img/prototypes/modelROS.gif"]
github = "https://github.com/toppers/hakoniwa-ros2sim"
+++

ロボットの制御にROS/ROS2を用いた箱庭プロトタイプモデルです．単体のロボットだけでなく，複数のロボットの連携動作も可能です．
ROSで一般的に用いられているGazeboよりも軽量でロボットや環境もUnity上で容易にカスタマイズすることができ、URDF形式のモデルの導入も行うことができます。

### 技術研鑽視点での狙い

- 一般的なロボット制御に用いられているROSも含めたシミュレーションの実行
- 複数のロボットを連携させたシミュレーションの実行

### その他の狙い
- ROSのロボットも導入可能とすることで、複数の制御機構が混在したシミュレーション環境を実現する

### 導入方法と使用方法

最小の構成と手順で試行できるパッケージを，下記のGitHubリポジトリで公開しています．ぜひ試してみてください．

- [toppers/hakoniwa-ros2sim: 箱庭 ROS シミュレータ](https://github.com/toppers/hakoniwa-ros2sim)

### 動作例のデモ

![modelROSdemo](/hakoniwa/img/prototypes/modelROS.gif)

---

#### 謝辞・特記事項：

TurtleBot3 の Unity パッケージの設計と作成にあたっては，宝塚大学 東京メディア芸術学部 吉岡章夫准教授および学部生の杉崎涼志さん，木村明美さんにご協力いただきました．

TurtleBot3 のUnity アセットは，株式会社ロボティズ様より提供いただいたデータを基に作成しています．ご協力いただき深く感謝いたします．
