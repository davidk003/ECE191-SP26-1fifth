# Lidar (Livox MID360)

## Setup

Connect to main power distribution board, 12V.

Driver reference:
<https://github.com/Livox-SDK/livox_ros_driver2>

User manual from Livox:
<https://terra-1-g.djicdn.com/851d20f7b9f64838a34cd02351370894/Livox/Livox_Mid-360_User_Manual_EN.pdf>

livox docs:
<https://livox-wiki-en.readthedocs.io/en/latest/tutorials/new_product/mid360/mid360.html>

Hardware and prerequisites:

- Acquire a 12-pin aviation connector(looks circular with a nut that needs to be tightened to ensure connection) that splits into 3 branches(One ethernet, One 12V power input, one other unused)
- Tighten the connector to the lidar, ensure you can ping the lidar IP. (Refer below to config to know what the IP is)
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

- MAKE SURE frame is set to `livox_frame` whn viewing output in rviz.
- CHECK that Livox is on the same network as the Jetson.
- If no point cloud/messages appear, re-check IP, network, and frame settings first.

## General ROS2 tips
- Make sure the ROS_DOMAIN_ID environment variable is the same across containers (echoing it and getting nothing means default 0)
- Make sure the ROS rmw_implementation is installed/set correctly.
- You can use `ros2 topic list` to view every possible topic on your network/device. (This does not guarantee the output stream, however, only that it can see the publisher)
- You can use `ros2 topic echo <topic path name>` to echo the output of a topic onto your shell. (This is equivalent to subscribing, so if echo is not working, it is likely you cannot subscribe from other nodes.
