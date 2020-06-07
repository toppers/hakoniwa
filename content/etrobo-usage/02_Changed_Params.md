+++
description = "Add some motion, shaking, pulsing, sliding and more"
title = "変更可能なパラメータ"
date = "2017-04-10T16:43:08+01:00"
draft = false
weight = 200
bref="Although it is quite easy to overuse animation effects, Kube makes it pretty easy to create meaningful, smooth and overall nice looking animation. Feel free to click every button below to see what it does, and then only use those effects that are essential to your project"
toc = true
script = 'animation'
+++
# 変更可能なパラメータ



## EV3のパラメータについて

------

今回のシミュレーション環境(Unity側)にはいくつかパラメータがありますので，その説明を行います．

まず，パラメータを参照するには，Hierarchyビューで，「EV3」を選択してください(下図)．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F11a57fef-9e2d-e0a0-ef76-af5f71fc5d09.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=2fdf76b9af97446c26fe08b5e484d631)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F11a57fef-9e2d-e0a0-ef76-af5f71fc5d09.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=2fdf76b9af97446c26fe08b5e484d631)

すると，InspectorビューにEV3のパラメータが表示されます．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F835e61c2-0ec6-b955-3e32-01ba535a1860.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=34989dc74c297f1639308d77c4282ba6)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F835e61c2-0ec6-b955-3e32-01ba535a1860.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=34989dc74c297f1639308d77c4282ba6)

以下，変更可能なパラメータを説明します(説明されていないものは変更しないでください)．
※これらのパラメータは，シミュレーション実行時に動的に変更も可能なものもあります．



## EV3 Actuator(Script)

------

### Port(動的変更不可)

Unity側のUDP受信ポート番号です．デフォルトでは54001です．

この値を変更する場合は，athrill側のパラメータ定義ファイル(device_config.txt)の以下も変更してください．

```
DEBUG_FUNC_VDEV_TX_PORTNO   54001
```

device_config.txt は，`athrill-sample/ev3rt/ev3rt-beta7-release/asp3/sdk/OBJ`直下にあります．



## EV3 Sensor(Script)

------

### Host(動的変更不可)

Athrillの配置マシンのIPアドレスです．
Unityと同じマシン上に配置する場合は，デフォルト値のままで良いです．

マシン負荷が高く，athrillとUnityを別マシンで動かす場合は，このIPアドレスを変更して対応ください．

### Port(動的変更不可)

Athrill側のUDP受信ポート番号です．デフォルトでは54002です．

この値を変更する場合は，athrill側のパラメータ定義ファイル(device_config.txt)の以下も変更してください．

```
DEBUG_FUNC_VDEV_RX_PORTNO   54002
```

device_config.txt は，`athrill-sample/ev3rt/ev3rt-beta7-release/asp3/sdk/OBJ`直下にあります．



## EV3 Monitor(Script)

------

### Power Const(動的変更可)

EV3のモータのパワーです．デフォルトで40としていますが，値を変更できます．

ただ，あまり大きい値を設定しすぎるとUnity側の問題か，物理的にありえないのかよくわかりませんが，EVロボットが吹っ飛びますので，ご注意ください．．．



## 照明のON/OFFについて

------

先述の通り，今回のデモでは，照明を３個用意しています．

- 全体照明１個
    - Directional Light
- スポットライト２個
    - Spot Light1
    - Spot Light2

それぞれの照明はシミュレーション実行時にON/OFFできます．
ON/OFFのさせ方は単純で，HierachyビューでON/OFFしたいライトを選択します．

すると，Inspectorビューに下図のように「Light」のチェックボックスが見えます．
このチェックボックスを外せばOFFになります．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fd14a2c69-1a29-7e92-9281-db2f2c6dfeb0.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=6cce316ca8400bfc1fd70ee8d93784b5)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fd14a2c69-1a29-7e92-9281-db2f2c6dfeb0.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=6cce316ca8400bfc1fd70ee8d93784b5)



## カラーセンサの状態

------

パラメータではないですが，カラーセンサの認識している状態を知りたくなることがあるかと思います．
そのため，カラーセンサの認識している値をUnityのパラメータ表示機能を利用して可視化しています．

参照するには，下図のようにHierarchyビューでColorSensorを選択してください．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fb1a7d803-a262-07bb-d2e3-cfdc188ae9ab.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=435eebd6c23b9982645643c53f8dc4c1)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fb1a7d803-a262-07bb-d2e3-cfdc188ae9ab.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=435eebd6c23b9982645643c53f8dc4c1)

そうすると，Inspectorビューに下図のように認識値(Rgb)が表示されます．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F487343b4-2303-046a-f819-42f058143bf7.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=17d4a51db5055db1f82b7a47bc56651c)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F487343b4-2303-046a-f819-42f058143bf7.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=17d4a51db5055db1f82b7a47bc56651c)

Rgbは，現在認識している色をそのまま表示しています．
Rgb_r,g,b には，カラーセンサで取得できる数値を表示しています．