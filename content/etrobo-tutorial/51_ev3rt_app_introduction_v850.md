+++
title = "単体ロボット向けシミュレータ導入手順"
draft = false
+++

### EV3ロボット制御プログラム

現時点の制御プログラムの開発フォルダは以下のフォルダで，制御プログラムは app.c です．  
※まだ暫定構成です．

v850版のathrill2を利用される場合は，以下のフォルダで作業してください．

```
$ ls athrill-sample/ev3rt/ev3rt-beta7-release/asp3/sdk/workspace
appdir  arg_sakura.txt  asp  athrillsample  deps  fstest  log.txt  Makefile
```

現状は，app.c/main_task で直接制御を行っています．  
コード断片は以下の通りです．

```
    while(1) {

    /**
     * PID controller
     */
#define white 100
#define black 10
        static float lasterror = 0, integral = 0;
        static float midpoint = (white - black) / 2 + black;
        {
            float error = midpoint - ev3_color_sensor_get_reflect(EV3_PORT_1);
            integral = error + integral * 0.5;
            float steer = 0.07 * error + 0.3 * integral + 1 * (error - lasterror);
            ev3_motor_steer(left_motor, right_motor, 10, steer);
            lasterror = error;
        }
        tslp_tsk(100000); /* 100msec */

    }
}
```

上記のアプリケーション実装時の注意点として，以下があります．

- ASP3(v850)版の場合
  - double型のデータを使うと athrill がデコードエラーとなる可能性がありますので，float型を推奨します．
  - ASP3は第三世代のカーネルなので，周期ハンドラ/APIのパラメータ単位がHRP(第二世代)とは違います．第三世代の単位はマイクロ秒ですが，第二世代の単位はミリ秒です．