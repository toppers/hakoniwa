+++
description = "ETロボコンを題材とした時間同期の仕組みの確立"
title = "単体ロボット向け"
draft = false
weight = 100
toc = false
script = 'animation'
+++

単体のSBCで構成される単体ロボットを対象とした箱庭プロトタイプモデルです．[ETロボコン](https://www.etrobo.jp/)を題材としています．  
組込みマイコン上のプログラムの振る舞いを，ロボット上の挙動と連携させて検証を進めることができます．

### 技術研鑽視点での狙い：

- 物理シミュレータとマイコンシミュレータ間の連携方法の検討
- 異なるシミュレータ間の時間同期の検討

### その他の狙い：

- ETロボコンユーザ層に箱庭を広める（広報活動）

{{< rawhtml >}}
<img src="/img/prototypes/modelA.png" width="700">
<br>
<br>
{{< /rawhtml >}}

### 導入方法

- [導入方法(TOP)]({{< ref "/etrobo-setup/etrobo-setup-index.md">}})

### 使用方法

- [使用方法(TOP)]({{< ref "/etrobo-usage/etrobo-usage-index.md">}})

### 動作例のデモ

![modelAdemo](/img/prototypes/modelAdemo.gif)

---

#### 謝辞・特記事項：

Unityパッケージの設計と作成にあたっては，宝塚大学 東京メディア芸術学部 吉岡章夫准教授および学部生の杉﨑涼志さん，木村明美さん，千葉純平さんにご協力いただきました．

HackEVのUnityアセットは，ETロボコン実行委員会より提供いただいたデータを基に作成しています．実行委員会の皆さまに深く感謝いたします．  
ただし本アセットはETロボコンの本番環境とは異なりますので，大会に参加予定の方はご注意ください．また，本アセットは，個人利用または教育利用に限定してご利用ください．
