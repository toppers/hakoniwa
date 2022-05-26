---
title: "制御プログラムの変更方法"
description: "[Getting Started 1] tb3の制御プログラムの変更方法を紹介します"
date: 2022-05-14T13:26:38+09:00
draft: true
bref: "[Getting Started 1] tb3の制御プログラムの変更方法を紹介します"
weight: 100
toc: false
script: 'animation'
---

### ソースコードの場所
今回のサンプルのtb3の制御プログラムは、
```/ros2/workspace/src/tb3/src/tb3ctrl.cpp``` に配置されています。
詳細は実際のコードを見て頂くとして主要な部分を紹介していきます。ページの最後にコードの抜粋を示します。


### 制御プログラムの概要
Unity上のロボットと制御プログラムとは、ROSで通信しています。
Unity上のロボットからはレーザースキャナから周囲360°の距離データが送られてきます。制御プログラムからはロボットの移動量を送信します。

この制御プログラムは、壁沿いに周回するような制御を行っています。do_forwardで前方の距離が一定以上あれば前進し、turn_rightでは右側の距離が一定以上であれば旋回します。

このように制御部分は非常に小さく、他はROSで通信するためのボイラープレートとなっています。
制御部分のパラメータを変えることで、自由にロボットを制御することができます。いろいろと書き換えて試してみてください。
なお、コードを書き換えた後は、Dockerのコンテナ内でbuild.bashを実行してプログラムのコンパイルを行ってください。

### 制御プログラムの抜粋
```
// ロボットのレーザースキャナから受け取る360°周囲の距離データ
typedef struct {
  double ranges[360];
} ScanDataType;
static ScanDataType scan_data;

// レーザースキャナから受け取ったデータのROSのコールバック関数。取得したデータをscan_data変数に保持する。
static void scanCallback(const sensor_msgs::msg::LaserScan::SharedPtr msg) {
  int i;
  for (i = 0; i < 360; i++) {
    scan_data.ranges[i] = msg->ranges[i];
  }
  return;
}

// Unity上のロボットの制御値
static geometry_msgs::msg::Twist cmd_vel;

static float get_forward_distance(void) {
  ... // 前方向の一定角度のうち一番近い距離を取得
}

static float get_right_distance(void) {
  ... // 右側の一定角度のうち一番近い距離を取得
}

static bool do_forward(void) {
  ... // 前方向に移動指示。cmd_vel.linear.x（前後方向）を増加させ送信
}

static bool turn_right(void) {
  ... // 右転回を指示。cmd_vel.angular.z値(ロボットの垂直軸回転角)を増加して送信
}

static void do_control(void) {
  ... // 周囲の距離に応じて処理を判定する
}

using namespace std::chrono_literals;

int main(int argc, char **argv) {
  char buffer[3][4096];

  // UnityとROSで連携するためのTOPIC名の設定
  if (argc > 1) {
    sprintf(buffer[0], "%s_tb3_node", argv[1]);
    sprintf(buffer[1], "%s_cmd_vel", argv[1]);
    sprintf(buffer[2], "%s_scan", argv[1]);
    printf("START: %s\n", argv[1]);
  }
  else {
    sprintf(buffer[0], "tb3_node");
    sprintf(buffer[1], "cmd_vel");
    sprintf(buffer[2], "scan");
    printf("START\n");
  }
  rclcpp::init(argc, argv);

  // ROSのPublisher, Subscriberの生成
  auto node = rclcpp::Node::make_shared(buffer[0]);
  auto publisher =
      node->create_publisher<geometry_msgs::msg::Twist>(buffer[1], 1);
  auto subscriber = node->create_subscription<sensor_msgs::msg::LaserScan>(
      buffer[2], 1, scanCallback);

  rclcpp::WallRate rate(10ms);

  // 制御ループ
  while (rclcpp::ok()) {
    do_control();
    publisher->publish(cmd_vel);

    rclcpp::spin_some(node);
    rate.sleep();
  }
  return 0;
}
```