+++
title = "単体ロボット向けシミュレータ導入手順"
draft = false
+++

# 箱庭用 EV3RT 開発環境のダウンロード



任意のフォルダ上で，athrillサンプル(athrill-sample)のプログラムを git clone してください．

なお，cloneする場所は，以下のように athrillと同じフォルダ階層で実施してください．

```
 |---athril
 |---athrill-target-v850e2m
 └---ev3rt-athrill-v850e2m
```

clone方法は以下の通りです．

```
$ git clone https://github.com/toppers/ev3rt-athrill-v850e2m.git
```

## サンプルアプリケーションのダウンロード

------

2種類のサンプルアプリケーションを用意しています．

こちらから git clone いただき，`hakoniwa-scenario-samples/single-robot`配下の全てのフォルダを  
`ev3rt-athrill-v850e2m/sdk/workspace` に配置ください．

```
$ git clone https://github.com/toppers/hakoniwa-scenario-samples.git
```
