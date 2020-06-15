+++
title = "単体ロボット向けシミュレータ導入手順"
draft = false
+++

# Unityのインストール・パッケージのインポート・通信方式の切替方法



## Unityのインストール

------

Unityのインストール方法は色々なサイト・書籍で紹介されておりますので，インストールください．

以下のサイト等が参考になるかと思います．

- https://tech-camp.in/note/technology/44408/



## 使用するUnityパッケージ

------

単体ロボット向けシミュレータで使用するUnityパッケージを2種類用意してあります．
どちらかのパッケージをご選択いただき，インポートを行ってください．

| 使用するUnityパッケージ          | 説明                                         |
| -------------------------------- | -------------------------------------------- |
| single-robot-HackEV.unitypackage |  HackEVを模した走行体モデルを使用しています  |
| ev3rt-simple-robot.unitypackage  |  シンプルな走行体モデルを使用しています      |

それぞれ下記からダウンロードしてください
- single-robot-HackEV.unitypackage
	- https://github.com/toppers/hakoniwa-Unity-HackEV/releases
- ev3rt-simple-robot.unitypackage
	- https://github.com/toppers/hakoniwa-Unity-SimpleCar/releases


## Unityパッケージのインポート

------

### Unity 起動

まず，インストールしたUnityを起動してください．  
無事起動すると以下のような画面が出ますので，右上の「新規作成」を選択し新規プロジェクト作成します．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F09b1d24e-17a6-11b6-f4e7-a32efd5107d0.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=71f7230879bf208b4317c3930f570998)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F09b1d24e-17a6-11b6-f4e7-a32efd5107d0.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=71f7230879bf208b4317c3930f570998)

次の選択画面で，「プロジェクト名」に適当なプロジェクト名を設定して，「作成」ボタンを押下してください．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fbf9174e4-9de5-900e-8ff7-dacaeb1de778.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=d494c6c1379648a895482a6be6fc5156)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fbf9174e4-9de5-900e-8ff7-dacaeb1de778.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=d494c6c1379648a895482a6be6fc5156)

成功すると，以下のようにUnityが起動します．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fed3b9d03-d11e-47f8-7986-bbc8ac7dcc28.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=6e3ec3c126454926deb57b59b238fc0a)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fed3b9d03-d11e-47f8-7986-bbc8ac7dcc28.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=6e3ec3c126454926deb57b59b238fc0a)



### Unityパッケージのインポート

※画像は`single-robot-HackEV.unitypackage`をインポートする際のものになります

Unity のメニューから，「Assets」⇒「Import Package」⇒「Custom Package...」と選択し，任意の unitypackageファイルを選択してください．

成功すると，下図の画面がポップアップされますので，素直に「Import」ボタンを押下してください．

{{< rawhtml >}}
<img src="/hakoniwa/img/single-robot/unityimport.PNG" width="300">
<br>
<br>
{{< /rawhtml >}}

成功するとProject/Scenes配下にToppers_Courseというシーンが追加されます．
Toppers_Courseをダブルクリックすると下図の画面が現れます．

{{< rawhtml >}}
<img src="/hakoniwa/img/single-robot/unity_HackEV.png" width="900">
<br>
<br>
{{< /rawhtml >}}


次に，シミュレーションに関わる設定を変更します．

Unity のメニューから，「Edit」⇒「Project Settings」を選択します．

「Time」  
`Fixed Timestep` を 0.001に，
`Time Scale` を 0.6に設定します．

{{< rawhtml >}}
<img src="/hakoniwa/img/single-robot/unity_setting_time.png" width="700">
<br>
<br>
{{< /rawhtml >}}

※`ev3rt-simple-robot.unitypackage`を使用する場合で，もしシミュレーションの動作が  
遅い場合には，`Fixed Timestep` を 0.01に，EV3 Motor(Script)の`Interval`を 0.0005に，  
`Max Diff Time`を 40000に設定してください．

「Quality」  
`Other`の`VSync Count` を Don't Sync に設定します．

{{< rawhtml >}}
<img src="/hakoniwa/img/single-robot/unity_setting_quality.png" width="700">
<br>
<br>
{{< /rawhtml >}}

これでインポート作業終了です．



## 通信方式の切替方法

------

athrillとUnity間での通信方式によって設定が異なります．
ご自身の環境に合わせて，どちらかの通信方式をご選択ください．
- [UDP版を使用する場合はこちら]({{< ref "61_unity_install_udp.md">}})
- [MMAP版を使用する場合はこちら]({{< ref "61_unity_install_mmap.md">}})

### MMAPについて

MMAPにすると嬉しい点としては以下が挙げられます．

- UDP のように通信ロストは発生しない(シミュレーション精度向上につながる)
- Unity と athrill 間のやりとりは共有メモリベースなので，高速になる(と思われる)
- 上記のとおり，精度向上と高速性を期待して試行してみましたが，精度は良くなりました(速度はあまり変化ないような?)．

ただし，デメリットとして以下が挙げられます．

- 1マシン前提での構成を余儀なくされる
  - UDPであれば，athrillを別PCに配置して負荷分散可能ですので．
