+++
title = "技術要素"
draft = false
weight = 50
toc = false
script = 'animation'
description = "箱庭を形成する技術要素の紹介"
bref = "箱庭を形成する技術要素を紹介します"
+++

### TOPPERSカーネル

[TOPPERSプロジェクト](https://toppers.jp)により開発されている，μITRON4.0仕様のスタンダードプロファイルを拡張した，オープンソースのリアルタイムカーネルです．
主な適用対象は，高い信頼性・安全性・リアルタイム性を要求される組込みシステムです．

[![TOPPERS](https://www.toppers.jp/imgs/logo.gif)](https://toppers.jp/)

### Athrill

箱庭の核である，CPU命令セットシミュレータです．    
箱庭WGメンバが中心となって開発を進めています．組込みマイコンおよびペリフェラルの挙動を命令レベルでデバッグ・機能検証することができます．現在はV850/RH850およびARMv7-Aが主なサポート対象です．

TOPPERSライセンスのもと，オープンソースで開発を進めています．
- https://github.com/toppers/athrill

{{< image src="/img/athrill.png" width="200" href="https://github.com/toppers/athrill" >}}


### mROS

ROS(Robot Operating System)の組込み向け軽量実行環境です．ホストPC上のROSマスタおよびROSノードに対する，組込みマイコンからの出版購読型通信を実現します．[東京大学 情報理工学系研究科 システム情報第8研究室](http://www.hal.ipc.i.u-tokyo.ac.jp)が中心となって開発を進めています．    
[複数ロボットの連携制御シミュレーション](/hakoniwa/prototypes/multi-robot)のようなシステムでの活用を想定しています．

- https://github.com/mROS-base

{{< image src="img/mROS.png" width="300" href="https://github.com/mROS-base" >}}

### RDBOX

RDBOX (Robotics Developers BOX)は，ROSロボットやIoTに最適化した，Kubernetesクラスタとセキュアで拡張性の高いWi-Fiネットワークを自動構築するためのフレームワークです．シミュレーション環境と現実の作業環境をブリッジすることを目指しています．株式会社インテックの[RDBOX Project](https://rdbox-intec.github.io/homepage_jp/)で開発されています．    
[ロボット間協調動作向けプロトタイプモデル](/hakoniwa/prototypes/harmony-robot)の構築において，箱庭との連携を進めています．

- https://github.com/rdbox-intec/rdbox

{{< rawhtml >}}
<a href="https://github.com/rdbox-intec/rdbox">
<img src="https://rdbox-intec.github.io/homepage_en/icons/icon-512x512.png" width="250">
</a>
<br>
<br>
{{< /rawhtml >}}

### Unity

リアルタイム3D開発プラットフォームです．IDEを内蔵するゲームエンジンとして有名です．    
箱庭では，物理演算エンジンと空間可視化のために活用しています．

- https://unity.com/

{{< rawhtml >}}
<br>
<a href="https://unity.com/">
<img src="https://meetup-uploads.unity3d.jp/2ec5b714ac553e261a155a0dc1b649406f9264a2.png" width="250">
</a>
<br>
<br>
<br>
{{< /rawhtml >}}

---
箱庭WGでは，この他にも，IoT／クラウドロボティクス時代の仮想環境を確立するために，統合すべき技術要素を模索しているところです．   
シナジーが生まれそうな技術や，活用できそうな知見をお持ちの方がいましたら，ぜひお知らせください．


{{< rawhtml >}}
<span style="font-size: 70%">
注：
このウェブページは，ユニティ テクノロジーズまたはその関連会社がスポンサーとなったり，ユニティ テクノロジーズまたはその関連会社と提携しているものではありません．
このサイトに掲載された <a href="https://unity3d.com/jp/legal/trademarks" target="_blank">Unity の登録商標一覧</a>に含まれる Unity の登録商標はすべて，ユニティ テクノロジーズまたはその米国や他の国々に所在する関連会社の登録商標または商標です．
</span>
{{< /rawhtml >}}


