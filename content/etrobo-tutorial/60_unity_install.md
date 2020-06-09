+++
title = "ETロボコンシミュレータ導入手順"
draft = false
weight = 200
toc = true
script = 'animation'
+++

# Unityのインストール・パッケージのインポート・初回に行う設定



## Unityのインストール

------

Unityのインストール方法は色々なサイト・書籍で紹介されておりますので，インストールください．

以下のサイト等が参考になるかと思います．

- https://tech-camp.in/note/technology/44408/



## 使用するUnityパッケージ

------

今回のデモ用ののUnityパッケージ(ev3rt-demo.unitypackage)は，以下にあります．

```
ls athrill-sample/ev3rt/ev3rt-beta7-release/unity/
ev3rt-demo1.0-1.unitypackage  ev3rt-demo1.0.unitypackage  ev3rt-demo1.1.unitypackage
```

なお，ETロボコンシミュレータで使用するUnityパッケージは，athrillとUnityの通信方式によって異なります．どちらかのパッケージをご選択いただき，インポートを行ってください．

| 通信方式 | 使用するUnityパッケージ      |
| -------- | ---------------------------- |
| UDP通信  | ev3rt-demo1.0.unitypackage   |
| MMAP     | ev3rt-demo1.0-1.unitypackage |

### MMAPについて

MMAPにすると嬉しい点としては以下が挙げられます．

- UDP のように通信ロストは発生しない(シミュレーション精度向上につながる)
- Unity と athrill 間のやりとりは共有メモリベースなので，高速になる(と思われる)
- 上記のとおり，精度向上と高速性を期待して試行してみましたが，精度は良くなりました(速度はあまり変化ないような?)．

ただし，デメリットとして以下が挙げられます．

- 1マシン前提での構成を余儀なくされる
  - UDPであれば，athrillを別PCに配置して負荷分散可能ですので．



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

Unity のメニューから，「Assets」⇒「Import Package」⇒「Custom Package...」と選択し，下図のように「ev3rt-demo1.0.unitypackage」を選択してください．

MMAP対応版をご利用される場合は，[ev3rt-demo1.0-1.unitypackage]を選択してください．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F54476ebb-958f-de77-48ad-6e80e06b0cd2.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=2e4f38a72a936c33a942e7aadbe34a17)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F54476ebb-958f-de77-48ad-6e80e06b0cd2.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=2e4f38a72a936c33a942e7aadbe34a17)

成功すると，下図の画面がポップアップされますので，素直に「Import」ボタンを押下してください．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fa2d57a43-20db-a084-3993-467c36761d38.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=a25ffa27270c01428595ccc0359ea28b)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fa2d57a43-20db-a084-3993-467c36761d38.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=a25ffa27270c01428595ccc0359ea28b)

成功するとProject/Scenes配下にRoboconSampleというシーンが追加されます(下図)．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fa671c5f2-bc53-f66c-6b3a-094ae51d5d36.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=255c03db25461addcdffa3a94401fd83)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fa671c5f2-bc53-f66c-6b3a-094ae51d5d36.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=255c03db25461addcdffa3a94401fd83)

RoboconSampleをダブルクリックすると下図の画面が現れます．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fa5da2d91-0857-4b63-bfa9-829204050699.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=40b63737bb172fc44d36ffbbce9acf3b)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fa5da2d91-0857-4b63-bfa9-829204050699.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=40b63737bb172fc44d36ffbbce9acf3b)

次に，シミュレーションの時間精度を1msecに変更します．  
Unityのメニューから「Edit」⇒「Project Settings」と選択し，下図のように「Fixed Timestep」を 「0.001」としてください．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F2848c388-ce6c-6464-aeb7-817a621fb6f6.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=ef9087eeb5ddbd6b4814dceccb94501b)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F2848c388-ce6c-6464-aeb7-817a621fb6f6.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=ef9087eeb5ddbd6b4814dceccb94501b)

なお，Fixed Timestepを0.001よりも大きい値にすることも可能です．シミュレーション精度は落ちますが，実行速度は速くなりますので，ご利用環境に応じて調整してください．  
MMAP版の場合は，0.01くらいでよいと思われます．

これでインポート作業終了です．



## 初回に行う設定

------
- [UDP版を使用する場合はこちら]({{< ref "61_unity_install_udp.md">}})
- [MMAP版を使用する場合はこちら]({{< ref "61_unity_install_mmap.md">}})