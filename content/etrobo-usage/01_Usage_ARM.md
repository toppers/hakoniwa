+++
description = "Add some motion, shaking, pulsing, sliding and more"
title = "ETロボコンシミュレータ使用手順(ARM版)"
date = "2017-04-10T16:43:08+01:00"
draft = false
weight = 200
bref="Although it is quite easy to overuse animation effects, Kube makes it pretty easy to create meaningful, smooth and overall nice looking animation. Feel free to click every button below to see what it does, and then only use those effects that are essential to your project"
toc = true
script = 'animation'
+++
# ETロボコンシミュレータ使用手順(ARM版)



## 使用手順

1. 環境変数の設定(Mac版のみ)
2. cfgフォルダの配置(初回起動時のみ)
3. ETロボコン制御プログラムのビルド
4. Unityのシミュレータの起動
5. athrillの起動



## 環境変数の設定(Mac版のみ)

------

Mac版の場合，gccインストールフォルダの環境変数の設定が必要になります．

```
export GCC_PATH=<gccインストールフォルダ>/gcc-arm-none-eabi-9-2019-q4-major
```



## cfgフォルダの配置(初回起動時のみ)

------

cfg ファイルの配置(Mac版の場合)

```
$ pwd 
<インストールフォルダ>/athrill-sample/ev3rt/ev3rt-beta7-release/asp_arm
$ cp cfg/cfg-mac cfg/cfg/cfg
$ chmod +x cfg/cfg/cfg
```

cfg ファイルの配置(Windows\Linux版の場合)

```
$ pwd 
<インストールフォルダ>/athrill-sample/ev3rt/ev3rt-beta7-release/asp_arm
$ cp cfg/cfg-linux-64 cfg/cfg/cfg
$ chmod +x cfg/cfg/cfg
```



## ETロボコン制御プログラムのビルド

------

ターミナル上で，`athrill-sample/ev3rt/ev3rt-beta7-release/asp_arm/sdk/OBJ`に移動して，ETロボコン制御プログラムをビルドしましょう．

ビルドするには，以下のコマンドを実行してください．

```
make clean;make
```

ビルド成功すると，asp というバイナリができます．

```
$ ls asp
asp
```



## Unityのシミュレータの起動

------

次に，Unityをシミュレーションモードにします．
Unityの画面上で[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F1365fe63-28e1-0b02-e615-91b1f23724b9.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=d95a1ef03fd2f1640baf832491fcc986)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F1365fe63-28e1-0b02-e615-91b1f23724b9.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=d95a1ef03fd2f1640baf832491fcc986)　ボタンを押下してください．

成功すると，下図のような画面に切り替わります．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F5fed7b18-1cbc-5fa5-a09a-9e9a66db97d7.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=7117483b2163bdcacc9e1cbb8d087bbe)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F5fed7b18-1cbc-5fa5-a09a-9e9a66db97d7.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=7117483b2163bdcacc9e1cbb8d087bbe)



## athrillの起動

------

WSLで，`athrill-sample/ev3rt/ev3rt-beta7-release/asp_arm/sdk/OBJ`に移動して，以下のコマンドを実行してください．

- unityとの通信が UDP の場合

```
$ athrill2 -c1 -m memory.txt -d device_config.txt -t -1 asp
```

- unityとの通信が MMAPの場合

```
$  bash simstart.bash
```

成功すると，以下のログが出力され，Unity上のEV3ロボットが動き始めます．

```
core id num=1
ROM : START=0x0 SIZE=512
RAM : START=0x5ff7000 SIZE=10240
Elf loading was succeeded:0x0 - 0xfd68 : 63.360 KB
ELF SYMBOL SECTION LOADED:index=22
ELF SYMBOL SECTION LOADED:sym_num=964
ELF STRING TABLE SECTION LOADED:index=23
athrill_device_func_call=0x60f7444

TOPPERS/ASP3 Kernel Release 3.2.0 for V850-ESFK3 (Nov  6 2019, 10:56:14)
Copyright (C) 2000-2003 by Embedded and Real-Time Systems Laboratory
                            Toyohashi Univ. of Technology, JAPAN
Copyright (C) 2004-2017 by Embedded and Real-Time Systems Laboratory
            Graduate School of Information Science, Nagoya Univ., JAPAN

brick_dri initialized.
   _____   ______ ___  ______
  / __/ | / /_  // _ \/_  __/
 / _/ | |/ //_ </ , _/ / /
/___/ |___/____/_/|_| /_/



Powered by TOPPERS/HRP2 RTOS
Initialization is completed..
System logging task is started.
```