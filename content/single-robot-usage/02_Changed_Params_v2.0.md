+++
title = "シミュレーションに関するチューニング"
draft = false
+++
## single-robot-HackEV(v2.0)の追加要素について

------

### Hakoniwaクラスの追加

`single-robot-HackEV(v2.0)` では`Hakoniwa`クラスが設けられました．  

{{< image src="/img/single-robot/unity_hierarchy_view_v2.0.png" width="400" >}}

`Hakoniwa`クラスはシミュレーション環境全体に関わる情報を持っています．

{{< image src="/img/single-robot/unity_hakoniwa_field.png" width="400" >}}


| 主なフィールド      | 説明                                                    |
| ------------------- | ------------------------------------------------------- |
| Max Diff Time       | athrillとUnityのシミュレーション時間の最大許容誤差時間  |
| Dbg Diff Time Msec  |  現在のathrillとUnityのシミュレーション時間の誤差(msec) |


### Robotの配置方法

`single-robot-HackEV(v2.0)`ではあらかじめ用意されたいくつかのロボットモデルを  
ユーザの方が任意に配置することが出来ます．

Project/Prefabs配下にいくつかのロボットモデルを用意しています．
{{< image src="/img/single-robot/unity_prefabs.png" width="600" >}}

これらのロボットモデルを`Hierarchy`ビューの`Robot`配下にドラッグ＆ドロップすることで
簡単に配置することができます．

{{< image src="/img/single-robot/unity_set_robot.gif" width="800" >}}

------

## 変更可能なパラメータ

------

### Robot のパラメータについて

------

#### 超音波センサ

{{< image src="/img/single-robot/unity_ultrasonic_sensor.png" width="300" >}}

`Ultrasonic Sensor`の`Distance Value`でセンサ範囲を調整できます．

{{< image src="/img/single-robot/unity_setting_ultrasonic_sensor.png" width="300" >}}

#### モーター

{{< image src="/img/single-robot/unity_tire.png" width="300" >}}

`Rigidbody`の`Mass`でタイヤの重さを，`Angular Drag`で回転時の抵抗値を調整できます．

{{< image src="/img/single-robot/unity_setting_tire.png" width="300" >}}

#### カラーセンサ

{{< image src="/img/single-robot/unity_color_sensor.png" width="300" >}}

`Physical Camera`の`Sensor Size`でセンシング範囲を調整できます．

{{< image src="/img/single-robot/unity_setting_color_sensor.png" width="300" >}}


#### センサ用ライト

{{< image src="/img/single-robot/unity_spot_light.png" width="300" >}}

`Light`の`Range`で光が届く範囲の距離を，`SpotAngle`で光が届く範囲の広さを調整できます．

{{< image src="/img/single-robot/unity_setting_spot_light.png" width="300" >}}