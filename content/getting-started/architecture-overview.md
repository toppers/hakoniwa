---
title: "箱庭のアーキテクチャ"
description: "[Getting Started 0] 箱庭のシステムアーキテクチャと動作の仕組みを紹介します"
date: 2022-05-14T13:26:27+09:00
draft: true
bref: "[Getting Started 0] 箱庭のシステムアーキテクチャと動作の仕組みを紹介します"
weight: 10
toc: false
script: 'animation'
---

### 前提環境
[箱庭 ROS シミュレータ:hakoniwa-ros2sim](https://github.com/toppers/hakoniwa-ros2sim)
を例題に解説するため、このチュートリアルが終わっておりプロジェクトが参照できることが望ましいです。

### ROS向け箱庭のシステム構成
ros2simのプロジェクトでは、Unity上のTortleBot3(tb3)をROS2のアプリから制御するシミュレーションを行います。
以下にWindows/WSL2でのシステム構成を示しています。大まかには制御対象であるUnity上のtb3とそれを制御するtb3ctrlがROSで通信しています。

![ROS向け箱庭のシステム構成](/hakoniwa/img/getting-started/ros2sim_overview.png)

### フォルダ構成
githubからCloneしたプロジェクトのフォルダ構成は以下のようになっています。主に/ros2/workspace, /ros2/unityを扱えばよく、
他のフォルダは本説明には含まれないため一旦無視してください。

- hakowani-ros2sim/
  - ros2/
    - workspace/  : ROSのワークスペース。Docker上にマウントされる
    - unity/tb3/  : Unityのプロジェクト

workspace/はROSのワークスペースで、ここに制御用のROSアプリを作成します。src下にはいくつかアプリが入っていますが、
tb3ロボットを制御しているのはtb3フォルダ下のソースとなります。
プログラムを修正した場合は```bash build.bash```を行うことでビルドされアプリが更新されます。

unity/はUnityプロジェクトが入っており、Unity Editorからtb3フォルダを開くと読み込めます。
cloneしたすぐの状態では、すべてのアセットは揃っておらずhako-install.bashによって必要なアセットのダウンロードや設定を行います。

### チュートリアルでの操作による挙動
- ```$ bash docker/pull-image.bash``` : 本プロジェクトで用いるROSが入ったDockerイメージの取得を行っています。
- ```$ bash docker/run.bash``` : 取得したDockerのコンテナを作成しbashでログインします。またこの時カレントディレクトリにworkspace以下をマウントしています。
- ```# bash hako-install.bash``` : unityフォルダにUnityのプロジェクトを展開すると共に、ROSと繋ぐための初期設定を行います。
- ```(Terminal A)$ bash run.bash``` : Dockerコンテナを起動しbashでログインします。
- ```(Terminal A)# bash launch.bash``` : UnityとROSで通信するための、ROS-TCP-Endpointを起動します。またUnityプロジェクトにはこのプログラムと対になる
- ```(Terminal B)$ bash attach.bash``` : Terminal Aで立ち上げたコンテナに入ります。
- ```(Terminal B)# bash run.bash``` : ロボットを制御するROSアプリのtb3ctrlを実行します。このプログラムのソースはworkspace/src/tb3/src/tb3ctrl.cppです。

### 