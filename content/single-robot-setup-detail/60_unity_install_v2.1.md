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

athrillとUnity間での通信方式に設定を行います．  
設定は`config.json`という設定ファイルを作成し，設定を行います．

#### config.json の設定例(通信方式がMMAPの場合)

設定するファイルパスは全て絶対パスで記述します．

```json
{
	"AthrillPath":"/mnt/c/project/esm/athrill/bin/linux/athrill2",
	"TerminalPath":"C:\\Windows\\System32\\wsl.exe",
	"robots":[
		{
			"RobotName":"RoboModel",
			"WorkspacePathWin":"C:\\project\\esm\\ev3rt-athrill-v850e2m\\sdk\\workspace",
			"WorkspacePathUnix":"/mnt/c/project/esm/ev3rt-athrill-v850e2m/sdk/workspace",
			"ApplicationName":"touch_sensor",
			"BinaryName":"asp"
		}
	]
}
```

#### config.json の設定例(通信方式がUDPの場合)

設定するファイルパスは全て絶対パスで記述します．

```json
{
	"AthrillPath":"/mnt/c/project/hakoniwa/athrill/bin/linux/athrill2",
	"TerminalPath":"C:\\Windows\\System32\\wsl.exe",
	"robots":[
		{
			"RobotName":"RoboModel",
			"WorkspacePathWin":"C:\\project\\hakoniwa\\ev3rt-athrill-v850e2m\\sdk\\workspace",
			"WorkspacePathUnix":"/mnt/c/project/hakoniwa/ev3rt-athrill-v850e2m/sdk/workspace",
			"ApplicationName":"touch_sensor",
			"BinaryName":"asp",
			"Udp":
			{
				"AthrillIpAddr":"127.0.0.1",
				"AthrillPort":54002,
				"UnityPort":54001
			}
		}
	]
}
```

#### 各設定パラメータについて

- **AthrillPath**  
  athrill2のパスを設定します．Windows版の場合は，WSL上でのパスを指定します．
- **TerminalPath**  
  ターミナルプログラムのパスを設定します．
  Windows版の場合は，wsl.exeのパスを設定します．  
  mac版の場合は，`/usr/bin/open`と記述します．
- **robots**  
  Unity上のRobot配下のロボット群を指します．複数のロボットにも対応しており，ここの中で各ロボット毎の設定を行うことが出来ます．  
  ロボットが1台の場合は，robots内の設定は1つとなります．
- **RobotName**  
  Unity上のRobot配下のロボットの名前を設定します．
- **WorkspacePathWin**  
  動作させるアプリケーションの実行環境のファイルパスを記述します．Windows版の場合はWindows上でのパスを設定します．  
  それ以外のプラットフォームの場合は，下記の`WorkspacePathUnix`と同じ値を設定してください．
- **WorkspacePathUnix**  
  動作させるアプリケーションの実行環境のファイルパスを記述します．Windows版の場合はwsl上でのパスを設定します．
- **ApplicationName**  
  動作させるアプリケーションのフォルダ名を設定します．
- **BinaryName**  
  athrillが実行するバイナリファイルの名前を設定します．特に名前変更などをしていない限り，ファイル名は`asp`となります．
- **Udp**  
  UDPとMMAPどちらの通信方式を使用するか設定します．MMAPを使用する場合は，この項目を省略してください．
- **AthrillIpAddr**  
  athrillを実行する端末のIPアドレスです．athrillを実行する端末とUnityを実行する端末が同じ場合は，`127.0.0.1`と設定していれば問題ありません．
- **AthrillPort**  
  athrillを実行する端末が空けている任意のポート番号を設定します．
- **UnityPort**  
  Unityを実行する端末が空けている任意のポート番号を設定します．

#### config.json を配置する

作成したconfig.jsonを使用しているUnityプロジェクトのフォルダ配下に配置します．

**例：Unityプロジェクトの名前が`single-robo`の場合**  
　→　`C:\UnityProjects\single-robo`直下

※`UnityProjects`はプロジェクト作成用に用意した任意のフォルダです．  
　ユーザがプロジェクトを作成したフォルダに置き換えてください．

### MMAPについて

MMAPにすると嬉しい点としては以下が挙げられます．

- UDP のように通信ロストは発生しない(シミュレーション精度向上につながる)
- Unity と athrill 間のやりとりは共有メモリベースなので，高速になる(と思われる)
- 上記のとおり，精度向上と高速性を期待して試行してみましたが，精度は良くなりました(速度はあまり変化ないような?)．

ただし，デメリットとして以下が挙げられます．

- 1マシン前提での構成を余儀なくされる
  - UDPであれば，athrillを別PCに配置して負荷分散可能ですので．
