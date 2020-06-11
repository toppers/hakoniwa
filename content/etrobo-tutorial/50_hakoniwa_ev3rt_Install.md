+++
title = "単体ロボット向けシミュレータ導入手順"
draft = false
+++

# 箱庭用 EV3RT 開発環境のダウンロード



任意のフォルダ上で，athrillサンプル(athrill-sample)のプログラムを git clone してください．

なお，cloneする場所は，以下のように athrillと同じフォルダ階層で実施してください．

```
 |---athril
 |---athrill-target
 └---athrill-sample
```

clone方法は以下の通りです．

```
$ git clone https://github.com/tmori/athrill-sample.git
```

開発環境一式は以下になります．

```
$ ls athrill-sample/ev3rt/ev3rt-beta7-release
$ $ ls
asp3     catkin_ws      EV3RT_C_API_Reference    hrp2.tar.xz        sdcard  webui
asp_arm  Changelog.txt  EV3RT_CPP_API_Reference  ngki_spec-171.pdf  unity
```