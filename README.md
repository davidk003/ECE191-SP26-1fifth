# ECE191 1-5th Car Documentation

This README is the main directory for project documentation. The guides below are migrated from the original `Github Documentation.pdf` notes, preserving the same step order, commands, and debugging emphasis.

## Documentation Directory

- [Jetson](jetson.md) - Flight checks, USB verification, ROS topic checks
- [Camera](camera.md) - DepthAI setup, baseline streaming tests, ROS camera nodes
- [YOLO](yolo.md) - CUDA/PyTorch validation and ROS2 YOLO node bring-up
- [VESC](vesc.md) - Steering/throttle wiring, flashing, and servo debug checks
- [LiDAR](lidar.md) - Livox MID360 setup, IP/network requirements, ROS launch
- [GNSS](gnss.md) - MosaicX5 serial setup, RMC/NMEA output commands, checks
- [Sensor Fusion](sensor-fusion.md) - Camera + LiDAR fusion workflow and calibration notes
- [Donkeycar](donkeycar.md) - Path follower runtime, Web UI, joystick drive mode
- [Path Following](path-following.md) - Record/save/erase controls and PID config references
- [Remote Controller](remote-controller.md) - ELRS flashing, pairing, and joystick verification

## Bring-Up Order (Run in This Order)

1. [Jetson](jetson.md) flight checks and ROS visibility checks
2. [Camera](camera.md), [LiDAR](lidar.md), and [GNSS](gnss.md) sensor bring-up
3. [YOLO](yolo.md) model/runtime validation and ROS node launch
4. [VESC](vesc.md) steering/throttle wiring and VESC Tool validation
5. [Remote Controller](remote-controller.md) ELRS pairing and joystick input checks
6. [Sensor Fusion](sensor-fusion.md) container workflow and calibration
7. [Donkeycar](donkeycar.md) + [Path Following](path-following.md)

## Important File References

- Donkeycar path settings and PID values: `~/projects/mycars/path_follower/myconfig.py`
- Donkeycar joystick trigger mapping: `~/projects/mycars/path_follower/my_joystick.py`

## Suggested Photos for Final Submission

- VESC power board and servo wiring path (`servo`, `5v`, `gnd`)
- Livox connector + Ethernet connection to Jetson
- GNSS/RC physical wiring chain and USB connections
- Checkerboard setup during camera-lidar extrinsic calibration
