+++
description = "Photonライブラリによる複数のROSロボットの連携とVR環境"
bref = "Photonライブラリによる複数のROSロボットの連携とVR環境"
title = "複数ロボットの連携制御シミュレーション"
draft = false
weight = 300
toc = false
script = 'animation'
images = ["img/prototypes/modelBoverview.png"]
github = "https://github.com/toppers/hakoniwa-ros-multiplay"
+++

複数のロボット，複数の制御プログラムによるシミュレーションを同じ環境で行うプロトタイプモデルです．
UnityのPhotonライブラリを用いて複数のUnity環境の同期を行っており，加えてアセット間の時間同期も実現しています．
またVRによるシミュレーション環境へのダイブも試行しています．

{{< image src="img/prototypes/modelBoverview.png" width="700" >}}

### 技術研鑽視点での狙い

- マルチ環境での連携方法検討（シミュレーション時間同期等）
- 箱庭アセット間の通信可視化方法の検討（ROS/ROS2連携含む）
- 箱庭アセットの仕組み検討

### その他の狙い

- ROSユーザ層に箱庭を広める（広報活動）

### 導入方法と使用方法

以下のGithubリポジトリにて，各種デモを公開しています．ぜひお試し下さい．

‐ [toppers/hakoniwa-ros-multiplay]("https://github.com/toppers/hakoniwa-ros-multiplay")

### 動作例のデモ
- photonによる複数ロボットの連携
{{< video src="/img/prototypes/modelBdemo1.mp4">}}
- Oculus Questとの接続の様子
{{< video src="/img/prototypes/modelBdemo2.mp4">}}
- VRで箱庭内に入った様子
{{< video src="/img/prototypes/modelBdemo3.mp4">}}

