# TWELITE for ROS

[Mono Wireless Inc.](https://mono-wireless.com)のTWELITE CUE(専用ソフトウェア:App_CUE)からのメッセージをLinuxで動作しているROSで受信できるようにするためのリポジトリです。

## Dependency

### 動作確認済みのバージョン

* TWELITE製品のファームウェアのバージョン
  * App_CUE_BLUE_L1304_P1-0-3
  * App_Wings_MONOSTICK_BLUE_L1304_P1-1-4
* ROSのバージョン
  * ROS Noetic Ninjemys
  * ROS2 Galactic Geochelone

## Setup

1. ROSの手順に従い自身のワークスペースに下記のフォルダを取り込んでください。
    * ROSの場合：  ros1_workspace
    * ROS2の場合： ros2_workspace
1. 自身の環境に合わせて```${ros_workspace}/src/app_cue/include/twelite_app_cue/config_twelite_app_cue.h```の内容を変更してください。
1. 上記の設定が完了したらROSのビルドを行ってください。

## Usage

1. MONOSTICKを動作するPCに接続してください。
1. ROSノードを実行してください。
   * （実行コマンド例）
       * ROSの場合 :  ```rosrun twelite_app_cue twelite_app_cue_node```
       * ROS2の場合 :  ```ros2 run twelite_app_cue twelite_app_cue_node```
1. 上記を実行するとTWELITEを受信すると```${ros_workspace}/src/twelite_interfaces/msg/TweliteAppCueMsg.msg```のカスタムメッセージが送信されます。

## License

This software is released under the MIT License, see LICENSE.

## Authors

https://github.com/MasterAkari

## References

| Name.                         | URL                                         |
| ----------------------------- | ------------------------------------------- |
| Mono Wireless Inc.            | https://mono-wireless.com                   |
| ROS Documentation             | http://wiki.ros.org/                        |
| ROS2 Documentation : Galactic | https://docs.ros.org/en/galactic/index.html |

## Note

TWELITE CUEの専用ソフトウエア キューアプリ（App_CUE）で動作確認しました。
下記のセンサー等の解析は行っておりません。

* センサー
  * Temperature
  * Humidity
  * Illuminance
  * DIO
  * EEPROM

解析コード

* ${ros_workspace}/src/app_cue/src/ConverterAppCue.cpp
