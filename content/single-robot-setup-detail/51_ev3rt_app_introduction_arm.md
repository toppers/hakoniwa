+++
title = "単体ロボット向けシミュレータ導入手順"
draft = false
+++

### EV3ロボット制御プログラム

現時点の制御プログラムの開発フォルダは以下のフォルダで，制御プログラムは app.c です．  
※まだ暫定構成です．

ARM版のathrill2を利用される場合は，以下のフォルダで作業してください．

```
$ ls athrill-sample/ev3rt/ev3rt-beta7-release/asp_arm/sdk/OBJ1.0/
app.c  app.cfg  app.h  arg_sakura.txt  device_config.txt  log.txt  Makefile  Makefile.inc  memory.txt
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
        tslp_tsk(100); /* 100msec */

    }
}
```

上記のアプリケーション実装時の注意点として，以下があります．

- ASP(ARM)版の場合
  - ASPは，第二世代カーネルなので，単位はミリ秒です．HRPと同じですね．
  - ARM版のathrillは，利用実績が少ないので，命令セットのデコードエラーになる可能性が高いです．
  - デコードエラーになった場合は，以下に issue を挙げていただければ対応します．
    - https://github.com/tmori/athrill-target
    - この際，調査用に頂きたい情報は以下になります．
        1. athrillが出力したエラーメッセージ  
            例．CPU(pc=<アドレス>) Exception!!
        1. エラー発生した箇所のアセンブラ命令コード(objdumpの結果)  
            例．arm-none-eabi-objdump -D asp | less  
            objdumpの出力書式は以下の通りです．  
            <アドレス>: <機械語(16進数) <アセンブラ命令> <オペランド>  
            athrillのエラーメッセージ出力されたアドレスについて，上記箇所をレポート頂ければ上記命令の追加対応が可能になります．