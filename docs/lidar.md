# Lidar (Livox MID360)

## Setup

Driver reference:
<https://github.com/Livox-SDK/livox_ros_driver2>

Hardware and prerequisites:

- Acquire a 12-pin aviation connector that splits into 3 branches.
- Tighten the connector to the lidar.
- Power can come from the power distribution board.
- Ethernet is the main data connection from lidar to Jetson; connect Ethernet to Jetson.
- Install Livox SDK before installing `livox_ros_driver2`.

## Config

- Lidar IP is based on the last 2 digits of the serial number.
- IP pattern is `192.168.1.1XX` where `XX` is the last two serial digits.
- Ensure your Livox driver config includes the correct lidar IP.
- LIVOX SDK MUST BE INSTALLED BEFORE DRIVER INSTALLATION.

## Launch

```bash
ros2 launch livox_ros_driver2 msg_MID360.launch
```

## Debug

- MAKE SURE frame is set to `livox_frame`.
- CHECK that Livox is on the same network as the Jetson.
- If no point cloud/messages appear, re-check IP, network, and frame settings first.
