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

※動作確認は`Unity 2020.1.0b9(64bit)`で行っております．  
　使用する場合はこれ以降のバージョンのUnityをインストールすることをお勧めします．

## Unityパッケージのインポート

------

### Unity 起動

まず，インストールしたUnityを起動してください．  
無事起動すると以下のような画面が出ますので，右上の「新規作成」を選択し新規プロジェクト作成します．

{{< image src="img/single-robot/unity_invoke.png" width="800" >}}

次の選択画面で，「プロジェクト名」に適当なプロジェクト名を設定して，「作成」ボタンを押下してください．

{{< image src="img/single-robot/unity_create_project.png" width="800" >}}

成功すると，以下のようにUnityが起動します．

{{< image src="img/single-robot/unity_start.png" width="800" >}}


### Unityパッケージのインポート

※画像は`single-robot-HackEV.unitypackage`をインポートする際のものになります

Unity のメニューから，「Assets」⇒「Import Package」⇒「Custom Package...」と選択し，任意の unitypackageファイルを選択してください．

成功すると，下図の画面がポップアップされますので，素直に「Import」ボタンを押下してください．

{{< image src="img/single-robot/unity_import.png" width="300" >}}

成功するとProject/Scenes配下にToppers_Courseというシーンが追加されます．
Toppers_Courseをダブルクリックすると下図の画面が現れます．

{{< image src="img/single-robot/unity_HackEV.png" width="900" >}}


次に，シミュレーションに関わる設定を変更します．

Unity のメニューから，「Edit」⇒「Project Settings」を選択します．

「Time」  
`Fixed Timestep` を 0.001に，
`Time Scale` を 0.6に設定します．

{{< image src="img/single-robot/unity_setting_time.png" width="700" >}}

※`ev3rt-simple-robot.unitypackage`を使用する場合で，もしシミュレーションの動作が  
遅い場合には，`Fixed Timestep` を 0.01に，EV3 Motor(Script)の`Interval`を 0.0005に  
設定してください．

「Quality」  
`Other`の`VSync Count` を Don't Sync に設定します．

{{< image src="img/single-robot/unity_setting_quality.png" width="700" >}}

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
