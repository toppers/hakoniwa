+++
title = "単体ロボット向けシミュレータ導入手順"
draft = false
+++

# UDP用Unity設定

Unityとathrillをリモートで通信する場合は，Unity側で以下の設定を行います．

Unity のメニューから，「Edit」⇒「Project Settings」を選択します．

「Player」  
`Other Setting`の`Scripting Define Symbols` に`VDEV_IO_UDP`と設定します．

{{< rawhtml >}}
<img src="/hakoniwa/img/single-robot/unity_setting_player_udp.png" width="700">
<br>
<br>
{{< /rawhtml >}}

# UDP用パラメータ設定

Unityとathrillをリモートで通信する場合は，以下のパラメータを設定する必要があります．

## 説明する上でのIPアドレスの構成例

Unity側のIPアドレス：192.168.11.32  
athrill側のIPアドレス：192.168.11.20

なお，IPアドレスの確認方法は以下のやり方でわかります．

### お使いのPCがLinux/WSLの場合

ターミナル上で ifconfig コマンドを叩いて，ethernetの inet addr の値を確認します．

```
$ ifconfig
eth0      Link encap:Ethernet  HWaddr 54:ee:75:b4:3c:96
          inet addr:192.168.11.32  Bcast:192.168.11.255  Mask:255.255.255.0
          inet6 addr: fe80::cc6d:70d3:a934:a61b/64 Scope:Unknown
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0
          RX bytes:0 (0.0 B)  TX bytes:0 (0.0 B)
```

### お使いのPCがWindowsの場合

Windows PowerShell を開いて，ipconfigを叩きます．

```
> ipconfig

Windows IP 構成


イーサネット アダプター イーサネット:

   リンクローカル IPv6 アドレス. . . . .: fe80::cc6d:70d3:a934:a61b%24
   IPv4 アドレス . . . . . . . . . . . .: 192.168.11.32
   サブネット マスク . . . . . . . . . .: 255.255.255.0
   デフォルト ゲートウェイ . . . . . . .: 192.168.11.1
```

## athrillのパラメータ

athrillを実行するフォルダ配下に，athrill制御用のパラメータ設定ファイル device_config.txt があります．  
そこに，以下のようにIPアドレスを定義してください．

```
DEBUG_FUNC_VDEV_TX_IPADDR       192.168.11.32
DEBUG_FUNC_VDEV_RX_IPADDR       192.168.11.20
```

DEBUG_FUNC_VDEV_TX_IPADDR には，Unity側のIPアドレスを設定します．  
DEBUG_FUNC_VDEV_RX_IPADDR には，athrill側のIPアドレスを設定します．

## Unityのパラメータ

Unity側は，EV3 Sensor(Script)のHostにathrill側のIPアドレスを設定してください．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fb60b76a3-b1d0-5fdf-c885-64bf5fd243d5.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=d5c2d376d13276fbd02721e42d698c1b)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fb60b76a3-b1d0-5fdf-c885-64bf5fd243d5.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=d5c2d376d13276fbd02721e42d698c1b)