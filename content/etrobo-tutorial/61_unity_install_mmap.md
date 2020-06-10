+++
title = "ETロボコンシミュレータ導入手順"
draft = false
weight = 200
toc = true
script = 'animation'
+++

# MMAP用パラメータ設定

MMAP版のパッケージ[ev3rt-demo1.0-1.unitypackage]をインストールされた場合は，MMAPの設定が必要になります．  
※なお，このページで紹介しているUnity画面の画像はWindows版のものです

設定する場所は，Unity の以下のスクリプト・パラメータ(Filepath)部分です．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Feed2a22a-e74b-9e8f-0774-6ca34783a6e4.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=b6a404498493184bdc1bcfe3d2749bad)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Feed2a22a-e74b-9e8f-0774-6ca34783a6e4.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=b6a404498493184bdc1bcfe3d2749bad)

インポート直後ですと，[EV3 Actuator] と [EV3 Sensor]の Filepath は空白です．  
ここに設定する値としては，athrillとUnity間で通信するためのMMAPファイルの絶対パスを指定します．

MMAPファイル自体は，以下の２ファイルが含まれています．

```
$ ls athrill-sample/ev3rt/ev3rt-beta7-release/asp3/sdk/OBJ/*.bin
athrill-sample/ev3rt/ev3rt-beta7-release/asp3/sdk/OBJ/athrill_mmap.bin
athrill-sample/ev3rt/ev3rt-beta7-release/asp3/sdk/OBJ/unity_mmap.bin
```

athrill_mmap.bin の絶対ファイルパスを，[EV3 Actuator]のFilepathに設定してください(設定例：下図)．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fbac2a522-ef60-83de-3847-593907d4caa3.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=7b5daec21b535117b589967d8817fa69)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fbac2a522-ef60-83de-3847-593907d4caa3.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=7b5daec21b535117b589967d8817fa69)

unity_mmap.bin の絶対ファイルパスを，[EV3 Sensor]のFilepathに設定してください(設定例：下図)．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F95b47a49-4904-16dd-f568-09d285afd2a1.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=c00912d532173b48318ebd94f6deec5a)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F95b47a49-4904-16dd-f568-09d285afd2a1.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=c00912d532173b48318ebd94f6deec5a)

以上でMMAPの設定は終わりです．