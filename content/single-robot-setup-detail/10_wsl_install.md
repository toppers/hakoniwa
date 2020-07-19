+++
title = "単体ロボット向けシミュレータ導入手順"
draft = false
+++

# WSLのインストール

------

Windows版の場合はWSLをインストールいただく必要があります．  
※注意点として，現時点(2020/6月)時点では，WSL2はご利用いただけません(WSL2とUnity間でUDP通信できないため)．

WSLのインストール方法は色々なサイトで紹介されておりますので，Ubuntu 18.04 LTSをインストールください．

以下のサイト等が参考になるかと思います．

- https://qiita.com/Aruneko/items/c79810b0b015bebf30bb

インストールが完了したら，aptパッケージを更新しておきます．  
(更新しないと後ほど行うgccのインストールで失敗することがあるためです)  

```
$ sudo apt update
```

aptパッケージを更新したら，あらかじめ以下をインストールしておきます
- gcc
- make

```
$ sudo apt install gcc
$ sudo apt install make
```
