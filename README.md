# ECE191 1-5th Car Documentation

## Documentation Directory

- [Jetson](docs/jetson.md) - Flight checks, USB verification, ROS topic checks
- [Camera](docs/camera.md) - DepthAI setup, baseline streaming tests, ROS camera nodes
- [YOLO](docs/yolo.md) - CUDA/PyTorch validation and ROS2 YOLO node bring-up
- [VESC](docs/vesc.md) - Steering/throttle wiring, flashing, and servo debug checks
- [LiDAR](docs/lidar.md) - Livox MID360 setup, IP/network requirements, ROS launch
- [GNSS](docs/gnss.md) - MosaicX5 serial setup, RMC/NMEA output commands, checks
- [Sensor Fusion](docs/sensor-fusion.md) - Camera + LiDAR fusion workflow and calibration notes
- [Donkeycar](docs/donkeycar.md) - Path follower runtime, Web UI, joystick drive mode
- [Path Following](docs/path-following.md) - Record/save/erase controls and PID config references
- [Remote Controller](docs/remote-controller.md) - ELRS flashing, pairing, and joystick verification

## Bring-Up Order (Run in This Order)

1. [Jetson](docs/jetson.md) flight checks and ROS visibility checks
2. [Camera](docs/camera.md), [LiDAR](docs/lidar.md), and [GNSS](docs/gnss.md) sensor bring-up
3. [YOLO](docs/yolo.md) model/runtime validation and ROS node launch
4. [VESC](docs/vesc.md) steering/throttle wiring and VESC Tool validation
5. [Remote Controller](docs/remote-controller.md) ELRS pairing and joystick input checks
6. [Sensor Fusion](docs/sensor-fusion.md) container workflow and calibration
7. [Donkeycar](docs/donkeycar.md) + [Path Following](docs/path-following.md)

## Important File References

- Donkeycar path settings and PID values: `~/projects/mycars/path_follower/myconfig.py`
- Donkeycar joystick trigger mapping: `~/projects/mycars/path_follower/my_joystick.py`

## Docs details

This repository uses Material for MkDocs. The published documentation content lives in `docs/`, while this root README stays as the GitHub landing page.

- Docs homepage source: [`docs/index.md`](docs/index.md)
- Planned site URL: <https://davidk003.github.io/ECE191-SP26-1fifth/>

## Docs Development

Install dependencies:

```bash
python -m pip install -r requirements-docs.txt
```

Run local preview server:

```bash
python -m mkdocs serve
```

Run strict build check:

```bash
python -m mkdocs build --strict
```
