+++
description = "トピックス・イベント案内"
title = "トピックス・イベント案内"
draft = false
bref = "過去のトピックスやイベントについてご案内します"
toc = true
+++
### 2025年

- 2025.12.22
  - リポジトリの更新リリース情報
    - [toppers/hakoniwa-ros2pdu v2.2.2](https://github.com/toppers/hakoniwa-ros2pdu/releases/tag/v2.2.2) (2025.12.22)
    - [toppers/hakoniwa-pdu-csharp v2.0.2](https://github.com/toppers/hakoniwa-pdu-csharp/releases/tag/v2.0.2) (2025.12.22)
    - [toppers/hakoniwa-drone-core v3.4.1](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v3.4.1) (2025.12.22)
    - [toppers/hakoniwa-drone-core v3.5.0](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v3.5.0) (2025.12.22)
      - [リリースノート](https://github.com/toppers/hakoniwa-drone-core/blob/main/docs/upgrade_v3.5.0.md)
- 2025.11.1
  - リポジトリの更新リリース情報
    - [toppers/hakoniwa-ros2pdu 2.2.1](https://github.com/toppers/hakoniwa-ros2pdu/releases/tag/2.2.1) (2025.10.23)
      - 不具合修正
    - [toppers/hakoniwa-drone-core v3.4.0](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v3.4.0) (2025.10.22)
      - MuJoCo 連携機能の追加
      - Gemini 連携機能の追加
      - Scratch 連携機能の追加
      - 箱庭ドローンPROユーザ向けの機能アップデート
    - [toppers/hakoniwa-drone-core v3.3.1](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v3.3.1) (2025.10.22)
    - [toppers/hakoniwa-core-cpp v1.1.1](https://github.com/toppers/hakoniwa-core-cpp/releases/tag/v1.1.1) (2025.10.16)
    - [toppers/hakoniwa-ros2pdu v2.2.0](https://github.com/toppers/hakoniwa-ros2pdu/releases/tag/v2.2.0) (2025.10.16)
      - javascript 対応
    - [toppers/hakoniwa-pdu-csharp v2.0.1](https://github.com/toppers/hakoniwa-pdu-csharp/releases/tag/v2.0.1) (2025.10.16)
    - [toppers/hakoniwa-webserver v1.0.1](https://github.com/toppers/hakoniwa-webserver/releases/tag/v1.0.1) (2025.10.16)
    - [toppers/hakoniwa-bridge v2.0.1](https://github.com/toppers/hakoniwa-bridge/releases/tag/v2.0.1) (2025.10.16)
- 2025.9.11
  - リポジトリの更新リリース情報
    - [toppers/hakoniwa-drone-core v3.3.0](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v3.3.0) (2025.9.11)
    - [toppers/hakoniwa-drone-core v3.2.2](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v3.2.2) (2025.9.11)
    - [toppers/hakoniwa-drone-core v3.2.1](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v3.2.1) (2025.8.15)
      - 箱庭コアを[旧版](https://github.com/toppers/hakoniwa-core-cpp-client)から[新版](https://github.com/hakoniwalab/hakoniwa-core-pro) へ刷新した
      - データ受信イベント機能
      - RPCサービス機能
- 2025.7.29
  - リポジトリの更新リリース情報
    - [toppers/hakoniwa-drone-core v3.2.0](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v3.2.0) (2025.7.29)
      * ライセンス案内の追加（PRO版リンク含む）
      * Unreal Engine 対応の明記
      * ドローンAPI・外部環境APIの紹介セクション追加
      * 他OSSとの比較追加（柔軟性、開かれた設計思想）
    - [toppers/hakoniwa-sim-csharp v2.0.0](https://github.com/toppers/hakoniwa-sim-csharp/releases/tag/v2.0.0) (2025.7.29)
      - package.json のバージョンが 1.0.0 → 1.2.3 へ
      - Plugins/linux ディレクトリと libshakoc.so、およびメタファイルが追加されています
      - Windows (shakoc.dll) や macOS (libconductor.dylib, libshakoc.dylib) 向けバイナリが更新
    - [toppers/hakoniwa-pdu-csharp v2.0.0](https://github.com/toppers/hakoniwa-pdu-csharp/releases/tag/v2.0.0) (2025.7.29)
      - HakoHeartbeat や HakoSystemTime などの Mavlink 系メッセージ、監視カメラ関連 (MonitorCameraCmd, MonitorCameraData) など複数の PDU クラスが新規追加
      - DisturbanceAtm、DisturbanceBoundary といった大気・境界条件を表すクラスが追加され、Disturbance クラスに新フィールドとして追加
      - AddTwoIntsRequest 等、サービス通信のためのメッセージとパケットクラスが新設
      - ドローン状態を保持する DroneStatus クラスが追加
      - Time など多くの既存メッセージファイルに using 句の追加やフィールド修正
      - 動的確保を行う DynamicAllocator を用いたエンコード処理へと更新され、可変長配列データをヒープ領域に展開する仕組みが導入
      - package.json のバージョンが 1.0.0 から 1.4.0 へ更新
    - [toppers/hakoniwa-webserver v1.0.0](https://github.com/toppers/hakoniwa-webserver/releases/tag/v1.0.0) (2025.7.29)
      - PDU リクエスト受信に対応
      - WebSocket 実装で RequestPduRead 受信時にサーバへリクエストを登録する処理を追加
      - 非同期送信用に _send_packet() と send_packet_threadsafe() を実装
      - HakoPduServer にオンデマンド PDU 読み出しキューを追加
      - リアルタイム同期用スクリプト real_time_syncher.py を新規追加
      - WebSocket 実装でイベントループを保持し、起動時に設定
    - [toppers/hakoniwa-ros2pdu v2.1.0](https://github.com/toppers/hakoniwa-ros2pdu/releases/tag/v2.1.0) (2025.7.29)
      - Python言語サポートの追加
      - PDU (Protocol Data Unit) のPythonクラスを自動生成する機能が追加
      - PythonでPDUの読み書きや変換を行うためのライブラリ、テンプレート、ユーティリティが多数追加
      - Hakoniwaサービスメッセージ機能の追加
      - ROSのServiceのように、リクエストとレスポンスを行うための新しいメッセージ型 (hako_srv_msgs) が追加
      - 新しいメッセージの追加:Disturbance (外乱)、DroneStatus (ドローン状態)、MonitorCamera (監視カメラ)
      - テストの拡充
      - ドキュメントの更新
      - PDUのバイナリ↔構造体変換処理のリファクタリングとバグ修正
    - [toppers/hakoniwa-core-cpp-client v2.0.1](https://github.com/toppers/hakoniwa-core-cpp-client/releases/tag/v2.0.1) (2025.7.29)
      - 外乱（disturbance）機能の追加
      - Hakoモニターカメラへのオフセット設定の追加
    - [toppers/hakoniwa-drone-core v3.1.9-1](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v3.1.9-1) (2025.7.25)
- 2025.6.27
  - リポジトリの更新リリース情報
    - [toppers/hakoniwa-drone-core v3.1.9](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v3.1.9) (2025.6.27)
    - [toppers/hakoniwa-conductor v2.0.0](https://github.com/toppers/hakoniwa-conductor/releases/tag/v2.0.0) (2025.6.26)
      - 最新バージョンの箱庭コア機能に対応
      - テスト環境を docker compose で再構築
      - READMEの整備
- 2025.5.29
  - リポジトリの更新リリース情報
    - [toppers/hakoniwa-drone-core v3.1.0](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v3.1.0) (2025.5.29)
      - 外部環境（風、温度）の正式サポート
      - WSL/DockerでのPython API連携対応
      - UnityのWebAvatarの大幅アップデート(hakoniwa-unity-droneのバージョンは[v3.1.0](https://github.com/hakoniwalab/hakoniwa-unity-drone/releases/tag/v3.1.0))
      - カメラ、LiDAR, 衝突検出、バッテリー対応、
      - 荷物運搬、ゲームコントローラ対応
      - 箱庭ドローンPROバイナリの不具合修正等
      - Windowsバイナリのアップデート(win.zip)
      - Windows Pythonライブラリ群(python.zip) 　※sharesim で連携する場合は必要となります。
- 2025.5.23
  - リポジトリの更新リリース情報
    - [hakoniwa-drone-core v3.0.1](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v3.0.1) (2025.5.18)
      - Windows / Mac / Linux のバイナリパッケージのアップデート
      - Windows Pythonライブラリのアップデート
- 2025.3.29
  - リポジトリの更新リリース情報
    - [hakoniwa-drone-core v3.0.0](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v3.0.0) (2025.3.26)
      - 大阪万博向けのイベントで利用する箱庭ドローンシミュレータの公開
      - 箱庭機能あり/無しの両方で利用できるように利用手順書とサンプルを公開
      - Windows / Mac / Linux のバイナリパッケージ
- 2025.3.11
  - リポジトリの更新リリース情報
    - [hakoniwa-drone-core v2.0.0](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v2.0.0) (2025.3.7)
      - PX4 連携のサンプルアプリ公開(<_os名_>-aircraft_service_px4)
      - Ardupilot 連携のサンプルアプリ公開(<_os名_>-aircraft_service_ardupilot)
      - 箱庭ドローンのサンプルアプリ公開(<_os名_>-drone_servce_rc)
      - 箱庭ドローンPro Cライブラリ公開(hako_service_c)
    - [hakoniwa-drone-core v1.0.0](https://github.com/toppers/hakoniwa-drone-core/releases/tag/v1.0.0) (2025.2.3)
    - [hakoniwa-sim-csharp v1.0.0](https://github.com/toppers/hakoniwa-sim-csharp/releases/tag/v1.0.0) (2025.1.4)
    - [hakoniwa-pdu-csharp v1.0.0](https://github.com/toppers/hakoniwa-pdu-csharp/releases/tag/v1.0.0) (2025.1.4)

### 2024年

- 2024.12.19
  - リポジトリの更新リリース情報
    - [hakoniwa-px4sim v2.8.0](https://github.com/toppers/hakoniwa-px4sim/releases/tag/v2.8.0) (2024.12.14)
      - バッテリー機能
      - 箱庭ARブリッジ機能
      - 箱庭ブリッジ(MAVLINK)
      - 東尋坊3Dモデルの公開
  - [技術情報・発表資料](/hakoniwa/technical-links/)のページの情報を更新しました。
    - SI2024(第25回計測自動制御学会システムインテグレーション部門講演会) が2024年12月18日(水)-20日(金)に開催され、箱庭WGのメンバが発表を行いました。
- 2024.11.30
  - リポジトリの更新リリース情報です。
    - [hakoniwa-px4sim v2.7.1](https://github.com/toppers/hakoniwa-px4sim/releases/tag/v2.7.1) (2024.11.15)
      - バグFIX
    - [hakoniwa-unity-drone-model v2.2.1](https://github.com/toppers/hakoniwa-unity-drone-model/releases/tag/v2.2.1)  (2024.11.4)
      - 箱庭PDU通信ライブラリの新アーキテクチャ対応
      - WebGLの荷物対応
      - QUEST3のWebSocket対応
- 2024.10.31
  - リポジトリの更新リリース情報です。
    - [hakoniwa-px4sim v2.7.0](https://github.com/toppers/hakoniwa-px4sim/releases/tag/v2.7.0) (2024.10.27)
      - Windows版インストーラ対応
      - Python APIの機能拡張
      - 環境シミュレーション機能（例：風の影響）の追加
      - 箱庭ドローンシミュレータのWebブラウザ対応
      - Python向け制御プログラムのリファクタリング
      - ARデバイス対応
      - 各種マニュアルのブラッシュアップ
    - [hakoniwa-unity-drone-model v2.2.0](https://github.com/toppers/hakoniwa-unity-drone-model/releases/tag/v2.2.0) (2024.10.20)
      - PC向けアプリ
      - AR体験向けアプリ
- 2024.08.24
  - リポジトリの更新リリース情報です。
    - [hakoniwa-unity-drone-model v2.1.1](https://github.com/toppers/hakoniwa-unity-drone-model/releases/tag/v2.1.1) (2024.08.15)
    - [hakoniwa-px4sim v2.6.0](https://github.com/toppers/hakoniwa-px4sim/releases/tag/v2.6.0) (2024.08.07)
      - Ubuntu 22.0.4の正式対応
      - ログリプレイ機能の追加
      - ドローン制御プログラムの評価ツールの追加
    - [hakoniwa-digital-twin](https://github.com/toppers/hakoniwa-digital-twin/releases/tag/digital-twin-real-model) (2024.07.01)
  - 新規のリポジトリ情報です。
    - [hakoniwa-webserver](https://github.com/toppers/hakoniwa-webserver) (2024.08.23)
      - 箱庭PDUをWebSocket経由でブラウザ上で可視化します。
    - [baremetal-athrill-v850e2m](https://github.com/toppers/baremetal-athrill-v850e2m) (2024.08.10)
    - [asp3-athrill-v850e2m](https://github.com/toppers/asp3-athrill-v850e2m) (2024.08.10)
      - Athrill向けTOPPERS/ASP3カーネルのパッケージ
- 2024.07.12
  - [チュートリアル](/hakoniwa/tutorial/)のページの情報を更新しました。
  - [チュートリアル](/hakoniwa/tutorial/)のページに箱庭入門会の動画アーカイブと資料を公開しました。
- 2024.06.24
  - リポジトリの更新リリース情報です。
    - 箱庭PDUで可変長データを対応しました。そのためPDUの構造が変更になりバージョンをv2系にしています。1系と2系の混在ではPDUの通信ができませんのでご注意ください。他の変更内容については各リポジトリのリリースノートを参照ください。
    - [hakoniwa-px4sim v2.5.0](https://github.com/toppers/hakoniwa-px4sim/releases/tag/v2.5.0) (2024.06.25)
    - [hakoniwa-unity-drone-model v2.1.0](https://github.com/toppers/hakoniwa-unity-drone-model/releases/tag/v2.1.0) (2024.06.25)
    - [hakoniwa-unity-tb3model v2.0.0](https://github.com/toppers/hakoniwa-unity-tb3model/releases/tag/v2.0.0) (2024.06.23)
    - [hakoniwa-px4sim v2.4.0](https://github.com/toppers/hakoniwa-px4sim/releases/tag/v2.4.0) (2024.06.14)
    - [hakoniwa-bridge v2.0.0](https://github.com/toppers/hakoniwa-bridge/releases/tag/v2.0.0) (2024.06.14)
    - [hakoniwa-core-cpp-client v2.0.0](https://github.com/toppers/hakoniwa-core-cpp-client/releases/tag/v2.0.0) (2024.06.14)
    - [hakoniwa-unity-simasset-plugin v2.0.0](https://github.com/toppers/hakoniwa-unity-simasset-plugin/releases/tag/v2.0.0) (2024.06.14)
    - [hakoniwa-ros2pdu v2.0.0](https://github.com/toppers/hakoniwa-ros2pdu/releases/tag/v2.0.0) (2024.06.14)
    - v1系のリリースとなります。
    - [hakoniwa-unity-simasset-plugin v1.0.1](https://github.com/toppers/hakoniwa-unity-simasset-plugin/releases/tag/v1.0.1)
    - [hakoniwa-ros2pdu v1.1.1](https://github.com/toppers/hakoniwa-ros2pdu/releases/tag/v1.1.1)
    - [hakoniwa-core-cpp-client v1.3.1](https://github.com/toppers/hakoniwa-core-cpp-client/releases/tag/v1.3.1)
- 2024.05.16
  - [リポジトリ一覧](/hakoniwa/repositories/)に開発中のリポジトリを追加しました。

[このページの先頭に戻る](#top)

### 2023年

- 2023.07.25
  - [チュートリアル](/hakoniwa/tutorial/)のページを作成しました。connpassにて開催している箱庭チュートリアル会のスライド資料や動画アーカイブなどを公開しています。
- 2023.07.23
  - 箱庭WGにおける研究開発の成果が[日本ロボット学会誌](https://www.rsj.or.jp/pub/jrsj/about.html)にレター論文として採録されました！
    - 高瀬 英希, 細合 晋太郎, 福田 竜也, 高田 光隆, 久保秋 真, 森 崇, **hakoniwa-ros2sim：仮想環境を活用したROS 2アプリケーションのシミュレーション手法**, 日本ロボット学会誌, 2023年41巻4号, pp. 399-402 (2023).
    - 論文公開先： <https://www.jstage.jst.go.jp/article/jrsj/41/4/41_41_399/_article/-char/ja>
  - 箱庭WGの活動成果「箱庭上でROS 2プログラムを手軽にシミュレーションできるhakoniwa-ros2simの一般公開」が TOPPERS of the YEAR 2023 を受賞しました！
  - 2022年6月30日(金)に開催された[TOPPERSカンファレンス2023の講演資料・動画](/hakoniwa/technical-links/#toppersカンファレンス2023)を掲載しました。
- 2023.01.07
  - 2022年度[TOPPERS活用アイデア・アプリケーション開発コンテスト](https://www.toppers.jp/contest.html)のアプリケーション開発部門において、金賞を受賞しました。
  - 受賞作品として[hakoniwa-ecu-multiplay](https://github.com/toppers/hakoniwa-ecu-multiplay)を公開しています。ぜひお試しください。

[このページの先頭に戻る](#top)

### 2022年

- 2022.09.08
  - 2022年9月1日(木)-2日(金)に開催された[SWEST24 (第24回 組込みシステム技術に関するサマーワークショップ)](/hakoniwa/technical-links/#swest24)にて実施したセッションの資料を掲載しました。
  - 2022年9月5日(月)-9日(金)に開催された[RSJ2022 (第40回 日本ロボット学会学術講演会)](/hakoniwa/technical-links/#rsj2022)にて実施したセッションの資料を掲載しました。
- 2022.08.27
  - 2022年8月26日(金)に開催された[ROS Japan UG #47 シミュレータ特集！](/hakoniwa/technical-links/#ros-japan-ug-47-シミュレータ特集)の講演資料を公開しました。
- 2022.06.27
  - 2022年6月25日(土)に開催された[ETロボコン向け TOPPERS活用セミナー](/hakoniwa/technical-links/#2022年度-etロボコン向け-toppers活用セミナー)の講義資料と動画を公開しました。
- 2022.06.15
  - [本Webサイトの英語版](/hakoniwa/en/)を公開しました。
  - 2022年6月10日(金)に開催された[TOPPERSカンファレンス2022の講演資料・動画](/hakoniwa/technical-links/#toppersカンファレンス2022)を掲載しました。
    - 「箱庭WGの活動紹介」 高田光隆（箱庭WG/名古屋大学）
    - 「ゲーム技術（VR/Photon）がもたらす箱庭ワールドの now and future」 森 崇（(株)永和マネジメント）
    - 「mROS 2：ロボットソフトウェアの組込みデバイス向け軽量実行環境」  高瀬英希（東京大学）
- 2022.06.02
  - 2022年5月28日(土)に開催された[オープンソースカンファレンス 2022 Nagoya](/hakoniwa/technical-links/#オープンソースカンファレンス-2022-nagoya)にて実施したセッションの資料を掲載しました。YouTube動画も公開されています。
- 2022.05.26
  - [Getting Started](/hakoniwa/getting-started) のページを公開しました。[hakoniwa-ros2sim](https://github.com/toppers/hakoniwa-ros2sim) を題材として、箱庭を用いたシミュレーションの進め方やカスタマイズ方法を案内していきます。コンテンツ内容は随時更新・追加していきますので、ぜひご確認ください。
- 2022.05.09
  - [hakoniwa-ros2sim](https://github.com/toppers/hakoniwa-ros2sim) を公開しました。箱庭上で ROS 2 プログラムを手軽にシミュレーションできます。ぜひお試しください。

[このページの先頭に戻る](#top)

### 2021年

- 2021.11.16
  - [Unity道場 ロボティクス 秋のLT祭り 2021](/hakoniwa/technical-links/#unity道場-ロボティクス-秋のlt祭り-2021)の講演資料および動画アーカイブが公開されました。
- 2021.11.10
  - [ROSCon JP 2021の講演動画のアーカイブ](/hakoniwa/technical-links/#roscon-jp-2021)が公開されました。
- 2021.09.16
  - [ROSCon JP 2021の講演資料](/hakoniwa/technical-links/#roscon-jp-2021)を掲載しました。
    - 箱庭:IoT/クラウドロボティクス時代の仮想シミュレーション環境  
    森崇 (永和システムマネジメント)・高瀬英希 (東京大学/JSTさきがけ)・福田⻯也 (インテック)
    - ROS 2 Client Library for E^2  
    高瀬 英希(東京大学/JSTさきがけ)、武田 大輝・今西 洋偉・祐源 英俊(京都大学)
- 2021.09.08
  - [ショーケース](/hakoniwa/showcase/)のページに、クラウドネイティブ環境上に構築した「箱庭」と「[RDBOX（Robotics Developer BOX）](https://github.com/rdbox-intec/rdbox)」を使って実現したROSロボットのCI（Continuous Integration，継続的インテグレーション）のデモ動画を掲載しました。
- 2021.09.05
  - 2021年9月2日(木)-3日(金)にオンライン開催された[SWEST23（第23回 組込みシステム技術に関するサマーワークショップ）](https://swest.toppers.jp/SWEST23/program/)のインタラクティブセッションにおいて、箱庭WGの活動およびWGメンバの研究開発の成果に関する次の発表が受賞しました。
    - ベストプロジェクト賞 ゴールド：TOPPERS箱庭WG紹介（発表者：森崇）
    - ベストポスター賞 ブロンズ：AUTOSAR 車両レベル仕様のビジュアル設計ツールの検討（発表者：高田光隆）
- 2021.07.09
  - 2021年6月26日(土)に開催された[ETロボコン向け TOPPERS活用セミナー](/hakoniwa/technical-links/#2021年度-etロボコン向け-toppers活用セミナー)の講義資料と動画を公開しました。
  - 2021年6月4日(金)に開催された[TOPPERSカンファレンス2021の講演資料・動画](/hakoniwa/technical-links/#toppersカンファレンス2021)を掲載しました。箱庭WGの活動紹介、箱庭コア技術の最新の開発状況、および、教育機会への箱庭成果物の活用事例について紹介しています。
    - 「［特別講演］Roboticsエンジニアチームの知的創造をブーストする ～クラウドネイティブ技術による開発革命～」 福田竜也（株式会社インテック　先端技術研究所）
    - 「『箱庭』Epilogue & Update 」 高瀬 英希（箱庭WG/東京大学)
    - 「最新の箱庭コア技術紹介」 森 崇（箱庭WG/永和システムマネジメント）
    - 「大学におけるシステム開発演習に箱庭を活用する」 久保秋 真（(株)チェンジビジョン）
    - 「ETロボコンでのathrill活用」 土樋 祐希（ETロボコン実行委員会）
  - [GitHub Discussions](https://github.com/toppers/hakoniwa/discussions)の運用を開始しました。箱庭に関わる開発者や技術者、ユーザのためのSNSになることを目指しています。お気軽にご投稿ください。
- 2021.06.28
  - 「[ROS で TOPPERS/箱庭・単体ロボット向けシミュレータを動かす！](https://qiita.com/kanetugu2018/items/a2a069dba6e26c4e7eda)」という解説記事をQiitaで公開しました。箱庭WGにおけるROSへの取り組みの最新情報をぜひチェックしてみてください。
- 2021.06.04
  - [ショーケース](/hakoniwa/showcase/)のページを作成しました。デモ動画やメディア掲載情報などを紹介していきます。
  - 箱庭の活動に協力いただいている宝塚大学より以下のプレスリリースが発表されました。  
    [「TOPPERSプロジェクト」単体ロボット向けシミュレータにデモ用モデルデータ制作で参加！宝塚大学東京メディア芸術学部ゲーム分野 学生の活躍](https://www.value-press.com/pressrelease/272584)
- 2021.05.26
  - [箱庭プロトタイプモデルA：単体ロボット向けシミュレータ](/hakoniwa/prototypes/single-robot/)を最小の構成・手順で試行できるパッケージをGitHubに公開しました。ぜひ試してみてください。  
  [toppers/hakoniwa-single_robot: 箱庭プロトタイプモデルA：単体ロボット向けシミュレータ](https://github.com/toppers/hakoniwa-single_robot)
- 2021.03.20
  - 最新の技術情報をフォローするための[Qiita記事へのリンク](/hakoniwa/technical-links/#qiita記事)を掲載しました。
  - [情報処理学会 第56回組込みシステム研究会 (ETNET2021)](https://www.ipsj.or.jp/kenkyukai/event/arc236sldm194emb56.html)にて発表した[研究論文](/hakoniwa/technical-links/#etnet2021)を掲載しました。
    - IoT仮想環境「箱庭」による自律移動ロボットの制御パラメータの自動探索手法
    - 立川 悠輝（京都大学）, 福田 竜也（インテック）, 森 崇（永和システムマネジメント）, 高瀬 英希（京都大学／JSTさきがけ）
  - [情報処理学会 第55回組込みシステム研究会](https://www.ipsj.or.jp/kenkyukai/event/emb55.html)にて発表した[研究論文およびスライド資料](/hakoniwa/technical-links/#情報処理学会-第55回emb研究会)を掲載しました。
    - IoT時代の仮想シミュレーション環境「箱庭」の実現に向けた検討および初期実装
    - 高瀬英希（京都大学／JSTさきがけ）, 細合晋太郎（チェンジビジョン）, 高田光隆（名古屋大学）, 庭野正義（アイコムシステック）, 辻悠斗, 森崇（永和システムマネジメント）

    [このページの先頭に戻る](#top)

### 2020年

- 2020年11月16日(月)から12月18日(金)にオンライン開催された[ET & IoT Digital 2020](https://www.jasa.or.jp/expo/2020/)の併設カンファレンス・スペシャルセッションにおける[講演資料および動画アーカイブ](/hakoniwa/technical-links/#et--iot-digital-2020)を掲載しました。
  - IoT/クラウドロボティクス時代の仮想シミュレーション環境「箱庭」のご紹介
  - 箱庭プロトタイプの紹介と開発状況
  - RDBOXが供するクラウドネイティブ環境を活用し「箱庭」を動かす
- ユニティ・テクノロジーズ・ジャパン様のWebページ「[Unityを活用した開発事例](https://industry.unity3d.jp/case.html)」にて、箱庭の活動が取り上げられています。"MANUFACTURE 製造分野でのUnity開発事例" の項目に掲載されています。
- 2020.12.13
  - 2020年11月26日(木)に開催された「[Modeling Forum 2020 〜モデリング x ニューノーマル〜](https://umtp-japan.org/event-seminar/9106)」における、箱庭の紹介とロボット教育への取り組み等の事例についての[講演資料および動画アーカイブ](/hakoniwa/technical-links/#modeling-forum-2020)を掲載しました。
    - 組込みシステムのモデリング／シミュレーションをデスクトップにもたらす＜箱庭＞の新世界
    - 森 崇（(株) 永和システムマネジメント）・久保秋 真（(株) チェンジビジョン）
  - [Unity開発事例ムービー "Made with Unity Reel 2020 [Industry]" ](https://www.youtube.com/watch?v=XlpoEYoVF7I)にて、箱庭が取り上げられています。箱庭の紹介は0:58頃の"Robot"にて登場します。ぜひご視聴ください。
- 2020.10.27
  - 2020年10月10日(土)に開催された[「Unity道場 ロボティクススペシャル 龍の巻」](https://meetup.unity3d.jp/jp/events/1257)の登壇レポートおよび動画が [Unity Learning Materials](https://learning.unity3d.jp/5167/) に掲載されました。
    - IoT/クラウドロボティクス時代の仮想シミュレーション環境・箱庭のご紹介
    - 森 崇（(株) 永和システムマネジメント・高瀬 英希（京都大学）
- 2020.08.26
  - [リポジトリ一覧](/hakoniwa/repositories)のページを追加しました。箱庭WGが開発・管理しているオープンソースソフトウェアを紹介しています。
  - 2020年8月20日(木)・21日(金)にオンライン開催された[SWEST22](https://swest.toppers.jp/SWEST22/program/)のインタラクティブセッションにおいて、箱庭WGの活動に関係する次の発表が受賞しました。
    - ベストプロジェクト賞 ゴールド：TOPPERS箱庭WG紹介（発表者：細合晋太郎・森崇）
    - ベストポスター賞 ゴールド：TOPPERS/Athrillを使用したAUTOSARモデルカー演習の実機レス化（発表者：庭野正義・安井大介）
- 2020.07.29
  - 2020年7月18日(土)に開催された[ETロボコン向け TOPPERS活用セミナー](/hakoniwa/technical-links/#2020年度-etロボコン向け-toppers活用セミナー)の動画アーカイブと講演資料を公開しました。
- 2020.06.12
  - 箱庭のWebサイトを立ち上げました。

[このページの先頭に戻る](#top)
