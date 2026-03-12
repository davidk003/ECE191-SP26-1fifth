# YOLO

## Setup (Native)

Complete camera setup first (see `camera.md`). For an initial visual test, run the minimal camera scripts in `camera.md` (`stream_UVC.py` + `cv_test.py`) before benchmarking YOLO.

Use the benchmark/setup reference here:
<https://github.com/davidk003/ece191-camera-bench>

Known-good environment from that repo:

- CUDA `11.4`
- Jetson / L4T `R35.4.1`
- NVIDIA Jetson PyTorch build: `torch 2.1.0a0+41361538.nv23.6`
- `torchvision 0.16.0+fbb4cc5`

On Jetson, prefer a CUDA-enabled NVIDIA/Jetson-compatible PyTorch install over a generic desktop CPU-only install.

Install or verify the Python packages used by the benchmark/setup scripts:

- `torch`
- `torchvision`
- `ultralytics`
- `numpy`
- `matplotlib`
- `scipy`

Before benchmarking, set the Jetson to max performance mode:

```bash
sudo nvpmodel -m 0
sudo jetson_clocks
```

Run the PyTorch/CUDA validation test first:

```bash
python3 tests/torch_test.py
```

This should confirm that CUDA is available and that PyTorch can actually run GPU operations successfully.

The benchmark expects an Ultralytics-compatible YOLO `.pt` weights file. Example benchmark command:

```bash
python3 performance/benchmarkYOLO_cpu_min.py models/Nick_v1.1_yolo12_fast.pt --imgsz 160 --seconds 30
```

This writes `CPU.txt` and `GPU.txt`. Then generate plots with:

```bash
python3 performance/gatherAndPlot.py
```

## CPU vs GPU

![CPU vs GPU FPS benchmark](https://github.com/davidk003/ece191-camera-bench/raw/master/performance/plots/fps_average.png)

The benchmark shows why we use GPU/CUDA instead of CPU for YOLO inference on the Jetson: CPU performance averages about `4.3 FPS`, while GPU performance averages about `32.3 FPS`. In practice, the GPU is fast enough for responsive real-time inference, while CPU inference is mainly useful as a fallback or debugging baseline.

## Setup as ROS2 Node

After native setup and benchmarking work correctly, run the ROS2 node.

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
- If the benchmark's GPU path is unexpectedly slow, re-run `python3 tests/torch_test.py` and confirm CUDA is actually available.
- If benchmarking fails entirely, verify the `.pt` model path first and make sure it is an Ultralytics-compatible weights file.

## Example ROS node output
- the proper output must be selected as a topic in rviz.

<img width="501" height="576" alt="image" src="https://github.com/user-attachments/assets/f41656e3-76ad-4b01-acb6-37404c939a4a" />

