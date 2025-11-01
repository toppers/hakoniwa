+++
description = "IoT／クラウドロボティクス時代の仮想シミュレーション環境"
title = "箱庭"
draft = false

+++


### トピックス・イベント案内

- 2024年12月8日(日)に 現地開催オフラインイベント を開催しました
  - [箱庭まつり #2 〜 今年の怒涛の成果を見て触れて総まとめ 〜 忘年会もあるよ](https://hakoniwa.connpass.com/event/336520/)
  - [アーカイブはYoutube](https://youtube.com/playlist?list=PLvZDKbhDfoh0TEnTo9NyI46qmxcIUw_HN&si=8F3T1PPXb5oIaXGE)からご覧いただけます。
- 2024年08月10日(土)に 現地開催オフラインイベント を開催しました
  - [箱庭まつり #1 〜ドローン！デジタルツイン！箱庭のセカイを体験しよう〜](https://hakoniwa.connpass.com/event/323118/)
  - [アーカイブはYoutube](https://youtube.com/playlist?list=PLvZDKbhDfoh1EMBdcNBYH0RV1wSFJycW4&si=twOGQgIgvae_5MpR)からご覧いただけます。
- 2024年7月11-12日に開催された [EdgeTech+ WEST 2024](https://www.jasa.or.jp/etwest/) のJASA(組込みシステム技術協会)パビリオンにおいてドローンWGの活動で箱庭WGの紹介と活用事例の発表を行いました。
  - [箱庭ドローンシミュレータの紹介と活用事例 ～リアル空間・バーチャル空間を使ったシミュレータの活用～](https://f2ff.jp/introduction/9242?event_id=etexpo-west-2024)
  Speaker:森 崇（箱庭ラボ)

[もっと見る](topics)

### 更新情報
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

[もっと見る](update)
