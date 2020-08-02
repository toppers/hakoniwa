+++
title = "単体ロボット向けシミュレータ導入手順"
draft = false
+++

# MMAP用Unity設定

UnityとathrillをMMAPで通信する場合は，Unity側で以下の設定を行います．

Unity のメニューから，「Edit」⇒「Project Settings」を選択します．

「Player」  
`Other Setting`の`Scripting Define Symbols` に`VDEV_IO_MMAP`と設定します．

{{< image src="/img/single-robot/unity_setting_player_mmap.png" width="700" >}}

# MMAP用パラメータ設定


※なお，このページで紹介しているUnity画面の画像はWindows版のものです

設定する場所は，Unity の以下のスクリプト・パラメータ(Filepath)部分です．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Feed2a22a-e74b-9e8f-0774-6ca34783a6e4.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=b6a404498493184bdc1bcfe3d2749bad)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Feed2a22a-e74b-9e8f-0774-6ca34783a6e4.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=b6a404498493184bdc1bcfe3d2749bad)

インポート直後ですと，[EV3 Actuator] と [EV3 Sensor]の Filepath は空白です．  
ここに設定する値としては，athrillとUnity間で通信するためのMMAPファイルの絶対パスを指定します．

MMAPファイル自体は，以下の２ファイルが```app.c```と同じフォルダに含まれています．

- athrill_mmap.bin
- unity_mmap.bin

unity_mmap.bin の絶対ファイルパスを，[EV3 Sensor]のFilepathに設定してください(設定例：下図)．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F95b47a49-4904-16dd-f568-09d285afd2a1.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=c00912d532173b48318ebd94f6deec5a)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2F95b47a49-4904-16dd-f568-09d285afd2a1.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=c00912d532173b48318ebd94f6deec5a)

athrill_mmap.bin の絶対ファイルパスを，[EV3 Actuator]のFilepathに設定してください(設定例：下図)．

[![image.png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fbac2a522-ef60-83de-3847-593907d4caa3.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=7b5daec21b535117b589967d8817fa69)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F244147%2Fbac2a522-ef60-83de-3847-593907d4caa3.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=7b5daec21b535117b589967d8817fa69)


例えば，v850版を使用するという前提で`ev3rt-athrill-v850e2m`のローカルリポジトリが，  
`C:\project\hakoniwa`にあり，実行したいアプリケーションのフォルダが`line_trace`の場合は，  
以下のパスを設定します．

- [EV3 Actuator]のFilePath  
`C:\project\hakoniwa\ev3rt-athrill-v850e2m\sdk\workspace\line_trace\unity_mmap.bin`

- [EV3 Sensor]のFilePath  
`C:\project\hakoniwa\ev3rt-athrill-v850e2m\sdk\workspace\line_trace\athrill_mmap.bin`

以上でMMAPの設定は終わりです．