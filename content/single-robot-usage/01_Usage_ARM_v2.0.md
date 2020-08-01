+++
title = "単体ロボット向けシミュレータ使用手順(ARM版)"
draft = false
+++
# 単体ロボット向けシミュレータ使用手順(ARM版)



## 使用手順

1. 環境変数の設定(Mac版のみ)
2. cfgフォルダの配置(初回起動時のみ)
3. EV3ロボット制御プログラムのビルド
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
<インストールフォルダ>/ev3rt-athrill-ARMv7-A
$ mkdir cfg/cfg
$ cp cfg/cfg-mac cfg/cfg/cfg
$ chmod +x cfg/cfg/cfg
```

cfg ファイルの配置(Windows\Linux版の場合)

```
$ pwd 
<インストールフォルダ>/ev3rt-athrill-ARMv7-A
$ mkdir cfg/cfg
$ cp cfg/cfg-linux-64 cfg/cfg/cfg
$ chmod +x cfg/cfg/cfg
```



## EV3ロボット制御プログラムのビルド

------

ターミナル上で，`ev3rt-athrill-ARMv7-A/sdk/OBJ1.1`に移動して，  
EV3ロボット制御プログラムをビルドしましょう．

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

成功すると，下図のような画面に切り替わります．(画像は single-robot-HackEV.unitypackage の場合)

{{< image src="/img/single-robot/unity_run.png" width="900" >}}


## athrillの起動

------

最後に，athrillを起動しましょう．

`ev3rt-athrill-ARMv7-A/sdk/OBJ1.1`に移動して，以下のコマンドを実行してください．

- unityとの通信が UDP の場合

UDP版の場合
```
$ athrill2 -c1 -t -1 -m memory.txt -d device_config.txt ../asp
```

MMAP版の場合
```
$ athrill2 -c1 -t -1 -m memory_mmap.txt -d device_config_mmap.txt ../asp
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

## シミュレータのデバッグ

------

下記のコマンドでathrillを実行すると，デバッグモードで実行することができます

UDP版の場合
```
$ athrill2 -c1 -i -t -1 -m memory.txt -d device_config.txt ../asp
```

MMAP版の場合
```
$ athrill2 -c1 -i -t -1 -m memory_mmap.txt -d device_config_mmap.txt ../asp
```

デバックモードの場合，athrillを実行しているコンソールにて`q`コマンドを入力し，Enterを押下することで，  
処理が停止します．  
処理が停止している間は，Unity側のシミュレータも動作を停止します．  
処理が停止している状態で，athrillを実行しているコンソールにて`c`コマンドを入力し，Enterを押下することで処理が再開します．

athrill実行時のデバッグコマンドの詳細についてはこちらをご確認ください．

- [athrill(アスリル)機能マニュアル(Qiita記事へのリンクです)](https://qiita.com/kanetugu2018/items/cf3dea16710a3f0737e8#%E3%83%9E%E3%83%8B%E3%83%A5%E3%82%A2%E3%83%AB)
