# Jetson

Use this page before launching any subsystem. These checks catch most bring-up failures quickly.

## Flight Checks

Run `lsusb` and confirm sensors/peripherals are detected by Linux.

```bash
lsusb
```

- If a sensor does not show up at all, there is usually a connection issue.
- Expected USB device labels:
  - Oak-D Pro W: `Intel Movidius MyriadX`
  - GNSS (MosaicX5): `Thesycon Systemsoftware & Consulting GmbH Septentrio USB Device`
  - Arduino: `STMicroelectronics Virtual COM Port` and `Arduino SA Leonardo (CDC ACM, HID)`
  - USB hubs: some variation of `USB hub`

## Power and Cabling Notes

- Use a power splitter for the camera when possible (separate power input and data output).
- Prefer a USB power hub (not only a data hub) to supply sensors/peripherals.

## Runtime Checks

- Use `top` or `jtop` (`jtop` is better for Jetson/GPU details).
- Use `ros2 topic list` to check active topics.
- Use `ros2 topic echo <topic_path>` to verify messages are actually publishing.

```bash
top
jtop
ros2 topic list
ros2 topic echo <topic_path>
```

`ros2 topic echo` is very important for debugging: a node can appear in topic list but still publish no output.
