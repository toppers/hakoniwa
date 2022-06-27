+++
title = "単体ロボット向けシミュレータ導入手順"
draft = false
+++

# MMAP用Unity設定

UnityとathrillをMMAPで通信する場合は，Unity側で以下の設定を行います．

Unity のメニューから，「Edit」⇒「Project Settings」を選択します．

「Player」  
`Other Setting`の`Scripting Define Symbols` に`VDEV_IO_MMAP`と設定します．

{{< image src="img/single-robot/unity_setting_player_mmap.png" width="700" >}}

# MMAP用パラメータ設定


※なお，このページで紹介しているUnity画面の画像はWindows版のものです

`Hierarchy`ビューで`Robot`配下の`RoboModel`を選択してください．  
すると画面右の`Inspector`ビューに[Io Writer (Script)]と[Io Reader (Script)]の項目が表示されます. 

{{< image src="img/single-robot/unity_hierarchy_view_robo_v2.0.png" width="300" >}}
{{< image src="img/single-robot/unity_setting_mmap_emp.png" width="300" >}}

インポート直後ですと，[Io Writer (Script)] と [Io Reader (Script)]の Filepath は空白です．  
ここに設定する値としては，athrillとUnity間で通信するためのMMAPファイルの絶対パスを指定します．

MMAPファイル自体は，以下の２ファイルが```app.c```と同じフォルダに含まれています．

- athrill_mmap.bin
- unity_mmap.bin

unity_mmap.bin の絶対ファイルパスを，[Io Writer (Script)]のFilepathに設定してください(設定例：下図)．

athrill_mmap.bin の絶対ファイルパスを，[Io Reader (Script)]のFilepathに設定してください(設定例：下図)．

{{< image src="img/single-robot/unity_setting_mmap.png" width="400" >}}

例えば，v850版を使用するという前提で`ev3rt-athrill-v850e2m`のローカルリポジトリが，  
`C:\project\hakoniwa`にあり，実行したいアプリケーションのフォルダが`line_trace`の場合は，  
以下のパスを設定します．

- [Io Writer (Script)]のFilePath  
`C:\project\hakoniwa\ev3rt-athrill-v850e2m\sdk\workspace\line_trace\unity_mmap.bin`

- [Io Reader (Script)]のFilePath  
`C:\project\hakoniwa\ev3rt-athrill-v850e2m\sdk\workspace\line_trace\athrill_mmap.bin`

以上でMMAPの設定は終わりです．