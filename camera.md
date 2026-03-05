# Camera

## Setup

Install DepthAI v2-compatible package (many scripts rely on v2):

```bash
pip install "depthai<3"
```

## Launch

### Baseline, least-modular run

From `~/ece191/Camera_fusion2025/src`:

Terminal 1:

```bash
python3 stream_UVC.py
```

Terminal 2:

```bash
python3 cv_test.py
```

`cv_test.py` uses OpenCV to open the camera stream.

This baseline test is the recommended first camera smoke test before trying ROS integrations.

### ROS node prototype (Python script)

Repository: <https://github.com/davidk003/ece191-camera-ros-prototype>

Run:

```bash
python3 oak_rgb_publisher.py
```

Read that repo README for optional runtime settings.

### Final ROS2 package

Repository: <https://github.com/davidk003/ece191-ros2-depthai-camera>

Use the 4 commands in quick start:
<https://github.com/davidk003/ece191-ros2-depthai-camera?tab=readme-ov-file#quick-start>

## Debug

- Validate node/topic visibility with `ros2 topic list`.
- Validate live stream data with `ros2 topic echo <topic_path>`.
- If a topic appears in `ros2 topic list` but has no messages, debug publisher startup and camera connectivity first.
