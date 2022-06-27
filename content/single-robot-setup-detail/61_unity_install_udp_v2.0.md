+++
title = "単体ロボット向けシミュレータ導入手順"
draft = false
+++

# UDP用パラメータ設定

UnityとathrillをUDPで通信する場合は，以下のパラメータを設定する必要があります．

**※ただし，1台のPCでシミュレーションを実行する場合は，以下の設定は不要です．**

### 説明する上でのIPアドレスの構成例

Unity側のIPアドレス：192.168.11.32  
athrill側のIPアドレス：192.168.11.20

なお，IPアドレスの確認方法は以下のやり方でわかります．

#### お使いのPCがLinux/WSLの場合

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

#### お使いのPCがWindowsの場合

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

### athrillのパラメータ

athrillを実行するフォルダ配下に，athrill制御用のパラメータ設定ファイル device_config.txt があります．  
そこに，以下のようにIPアドレスを定義してください．

```
DEBUG_FUNC_VDEV_TX_IPADDR       192.168.11.32
DEBUG_FUNC_VDEV_TX_PORTNO   	54001
DEBUG_FUNC_VDEV_RX_IPADDR       192.168.11.20
DEBUG_FUNC_VDEV_RX_PORTNO   	54002
```

DEBUG_FUNC_VDEV_TX_IPADDR には，Unity側のIPアドレスを設定します．  
DEBUG_FUNC_VDEV_RX_IPADDR には，athrill側のIPアドレスを設定します．

### Unityのパラメータ

`Hierarchy`ビューで`Robot`配下の`RoboModel`を選択してください．  
すると画面右の`Inspector`ビューに[Io Writer (Script)]と[Io Reader (Script)]の項目が表示されます. 

{{< image src="img/single-robot/unity_hierarchy_view_robo_v2.0.png" width="300" >}}

- Io Writer (Script)  
 Hostにathrill側のIPアドレスを設定してください．  
 Portには`DEBUG_FUNC_VDEV_RX_PORTNO`で設定した値を設定してください．

- Io Reader (Script)  
 Portには`DEBUG_FUNC_VDEV_TX_PORTNO`で設定した値を設定してください．
	
{{< image src="img/single-robot/unity_setting_udp.png" width="400" >}}
