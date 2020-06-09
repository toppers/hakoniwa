+++
title = "ETロボコンシミュレータ導入手順"
draft = false
weight = 200
toc = true
script = 'animation'
+++

# athrill2のインストール



## athrill2のインストール手順

------

- athrill のチェックアウト
- athrill-target のチェックアウト
- コンパイラのインストール
- ビルド＆インストール



## athrill のチェックアウト

------

athrill は，設計上，CPUアーキに依存しない共通コードとCPU依存するコードを分離しています．

共通コードのチェックアウトは，以下の通りです．

```
$ git clone https://github.com/tmori/athrill.git
```



## athrill-target のチェックアウト

------

CPUアーキに依存するコードは，athrill-target側で管理しています．  
今回のV850対応版は，ここにあります．

```
$ git clone https://github.com/tmori/athrill-target.git
```

なお，athrill と athrill-targetを以下のフォルダ構成にしてください．

```
.
├── athrill
└── athrill-target
```



## コンパイラのインストール

------

Linux の方は，gcc をインストールください．  
Windows の方は，WSL上で gcc をインストールください．  
Mac の方は，clang をインストールください．



## ビルド＆インストール

------

ビルド方法ですが，端末上でathrill-target/v850e2m に移動してください．

Linux/Windowsの方は，さらに build_linux に移動してください．  
Macの方は，build_mac に移動してください．

移動終わったら，以下コマンド実行するだけです．

```
make clean;make
```

ビルド成功すると，athrill側の bin/linux 配下に athrill2 というバイナリが配置されるはずです．

```
$ ls -l ../../../athrill/bin/linux/athrill2 
-rwxr-xr-x  1 tmori  staff  628260  2  2 16:40 ../../../athrill/bin/linux/athrill2
```

そして，このパスを .bashrcに登録してもらえれば，インストール終了です．  
以下，設定例です．

```
export PATH=<athrill配置フォルダパス>/athrill/bin/linux:${PATH}
```

