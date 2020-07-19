+++
title = "単体ロボット向けシミュレータ導入手順"
draft = false
+++

# linux版64bit gccコンパイラ(ライブラリ含む)のインストール

------

v850版のathrill2を利用される場合は，以下のサイトからコンパイラおよびライブラリ(athrill-gcc-package.tar.gz)をダウンロードください．

- https://github.com/toppers/athrill-gcc-v850e2m/releases/tag/v1.1

```
$ tar xzvf athrill-gcc-package.tar.gz
$ cd athrill-gcc-package/
$ tar xzvf athrill-gcc.tar.gz
$ ls usr/local/athrill-gcc/
bin  include  lib  libexec  share  v850-elf
```

解凍後，usr/local/athrill-gccを /usr/local 直下に移動してください．

```
$ sudo mv usr/local/athrill-gcc /usr/local
```

あとは，.bashrc に以下のパスを設定するだけです．

```
export PATH=/usr/local/athrill-gcc/bin/:${PATH}
export LD_LIBRARY_PATH=/usr/local/athrill-gcc:/usr/local/athrill-gcc/lib:${LD_LIBRARY_PATH}
```

設定後は，パスの有効化を忘れずに行ってください．

```
source ${HOME}/.bashrc
```