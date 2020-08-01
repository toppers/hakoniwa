+++
title = "単体ロボット向けシミュレータ導入手順"
draft = false
+++

# Unityのインストール・パッケージのインポート・通信方式の切替方法



## Unityパッケージのダウンロード
------

単体ロボット向けシミュレータで使用するUnityパッケージを2種類用意してあります．
どちらかのパッケージをご選択いただき，ダウンロードを行ってください．

| 使用するUnityパッケージ          | 説明                                         |
| -------------------------------- | -------------------------------------------- |
| single-robot-HackEV |  HackEVを模した走行体モデルを使用しています  |
| ev3rt-simple-robot  |  シンプルな走行体モデルを使用しています      |
| single-robot-HackEV(v2.0)  |  上記２つのモデルを含んでおり自由に選択できます      |

それぞれ下記からダウンロードしてください
- single-robot-HackEV.unitypackage
	- https://github.com/toppers/hakoniwa-Unity-HackEV/releases/tag/v1.0
- ev3rt-simple-robot.unitypackage
	- https://github.com/toppers/hakoniwa-Unity-SimpleCar/releases
- single-robot-HackEV.unitypackage(v2.0)
	- https://github.com/toppers/hakoniwa-Unity-HackEV/releases/tag/v2.0
------

使用するUnityのパッケージによって，設定画面のレイアウトが異なりますため，  
ご選択いただいたUnityパッケージに合わせた導入手順をご参照ください

- Unityのインストール・パッケージのインポート・通信方式の切替方法
	- [single-robot-HackEV(v2.0) を使用する場合]({{< ref "60_unity_install_v2.0.md">}})
	- [single-robot-HackEV または ev3rt-simple-robot を使用する場合]({{< ref "60_unity_install_v1.0.md">}})
