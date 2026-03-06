# YOLO

## Setup (Native)

- Ensure CUDA (with a compatible version) is installed.
- Complete camera setup first (see `camera.md`).
- For an initial visual test, run the minimal camera scripts in `camera.md` (`stream_UVC.py` + `cv_test.py`) before benchmarks.
- Run setup validation tests and benchmarks using:
  <https://github.com/davidk003/ece191-camera-bench>
- Follow that README to verify PyTorch + CUDA compatibility and run performance benchmarks.

## Setup as ROS2 Node

Expected topics for vehicle detection:

- `/yolo/detections`
- `/yolo/annotated`

Commands:

```bash
cd ~/dai_ws
colcon build --packages-select yolo_ros2
source install/setup.bash
cd ~/ece191/Camera_fusion2025/src
ros2 run yolo_ros2 yolo_node
```

## Debug

- Confirm topics with `ros2 topic list`.
- Confirm data is publishing with `ros2 topic echo /yolo/detections`.
- Optionally verify image output with `ros2 topic echo /yolo/annotated`.
- If topics exist but no messages, validate camera pipeline first.
