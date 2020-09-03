+++
title = "単体ロボット向けシミュレータ使用手順(V850版)"
draft = false
+++
# 単体ロボット向けシミュレータ使用手順


## V2.1での変更点について

v2.1 で，Unityでのシミュレーション実行をビルドしてバイナリ実行できるようになりました．  
バイナリ実行でシミュレーション実行を行う場合，

- Unityシミュレーションの実行，  
- athrillの実行

をひとまとめにして実行することができます．

なお，従来の使用方法でもシミュレーションを実行することは可能ですので，  
その場合は下記をご参照いただき，使用してください．

- [V850版]({{< ref "01_Usage_V850_v2.0.md">}})
- [ARM版]({{< ref "01_Usage_ARM_v2.0.md">}})

これ以降は，バイナリ実行を行うための手順の紹介となります．

## 使用手順

1. ビルド設定
1. ビルドの実行，config.jsonの配置
1. シミュレーションの実行

## ビルド設定

------
ビルドを実施する前に，バイナリ実行時のウィンドウサイズに関する設定を行います．  
Unity のメニューから，「Edit」⇒「Project Settings」を選択します．

「Player」  
`Resolution and Presentation`の`Fullscreen Mode` を`Windowed`と設定します．
その下の詳細なウィンドウサイズは基本そのままでもよいですが，サイズを変更したい場合は，  
お使いの環境に合わせて変更してください．

{{< image src="/img/single-robot/unity_build_setting.png" width="600" >}}


## ビルドの実行，config.jsonの配置

------
設定が完了したら，Unityプロジェクトのビルドを行います．  
Unity のメニューから，「File」⇒「Build Settings」を選択します．

Platform は[PC,Mac & Linux Standalone]のままとします．  
`Architecture`は実行するPCのアーキテクチャに合わせて設定しますが，  
どちらか分からないという方は，`x86_64`を選択してください．

{{< image src="/img/single-robot/unity_build_platform_setting.png" width="600" >}}

設定を終えたら，`Build`を押下してビルドを実行します．

{{< image src="/img/single-robot/unity_build.png" width="400" >}}

すると，どの場所にビルドしたバイナリを配置するか，選択ダイアログが表示されますので，
任意の場所を選択します．  
今回は例として，ビルドするUnityプロジェクトのあるフォルダ内に，`Build`フォルダを作成し，  
その中にビルドしたバイナリを配置するようにします．

{{< image src="/img/single-robot/unity_build_import.png" width="400" >}}

フォルダを選択すると，ビルドが実行されます．

------
ビルドが完了したら，バイナリが出力されたフォルダ(今回の例では`Build`フォルダ)内に  
先ほど，Unityプロジェクトフォルダ配下に配置した**config.json**をコピーします．

## 制御アプリのビルド

------
シミュレーションの実行の前に制御アプリのビルドを行います．  
ビルド手順は，以下の`EV3ロボット制御プログラムのビルド`をご参照ください．

- [V850版]({{< ref "01_Usage_V850_v2.0.md">}})
- [ARM版]({{< ref "01_Usage_ARM_v2.0.md">}})


### memory_mmap.txtの編集(通信方式にMMAPを使用する場合のみ)
------

制御アプリのビルドが完了したら，Unityバイナリ実行のためにアプリケーションフォルダにある  
`memory_mmap.txt`を編集します．  
使用するMMAPファイルのパスを記述するのですが，Unityバイナリを使用する場合には，  
MMAPファイルのパスを**絶対パス**で記述するように変更します．

**例：アプリケーション名が`line_tarce`の場合のmemory_mmap.txt**

```
ROM, 0x00000000, 512
RAM, 0x00200000, 512
RAM, 0x05FF7000, 10240
RAM, 0x07FF7000, 10240
MMAP, 0x40000000, /mnt/c/project/hakoniwa/ev3rt-athrill-v850e2m/sdk/workspace/line_trace/athrill_mmap.bin
MMAP, 0x40010000, /mnt/c/project/hakoniwa/ev3rt-athrill-v850e2m/sdk/workspace/line_trace/unity_mmap.bin
```

## シミュレーションの実行

------
ビルドが完了したら，シミュレーションを実行します．  
先ほど選択したフォルダにビルドしたバイナリが作成されていますので，
`<プロジェクト名>.exe`または`<プロジェクト名>.app`のファイルを実行することでシミュレータが起動します．

{{< image src="/img/single-robot/unity_binary_start.png" width="400" >}}

起動した画面上で`実行`ボタンを押下すれば，シミュレーションが実行されます．

{{< image src="/img/single-robot/unity_binary_sim_start.png" width="600" >}}
