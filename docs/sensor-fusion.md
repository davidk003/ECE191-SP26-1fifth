# Sensor Fusion (Camera + Lidar)

Reference repository:
<https://github.com/davidk003/ros2_camera_lidar_fusion>

This section corresponds to the original "Sensor Fusion Car2" workflow notes.

## Workflow (Run in Order)

1. Launch camera node.
2. Launch lidar node.
3. In `ros2_camera_lidar_fusion/docker`, build once:

```bash
sh build.sh
```

4. Launch container:

```bash
sh run.sh
```

5. Inside container, verify topics:

```bash
ros2 topic list
```

## Calibration Note

During `extrinsic_camera_calibration`, hold a black-and-white checkerboard pattern (at least `7x7` squares visible, based on original notes).

## Suggested Evidence to Capture

- Camera topic list output inside container
- Lidar topic list output inside container
- A photo/screenshot of checkerboard setup during calibration
