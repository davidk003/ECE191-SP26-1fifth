# Remote Controller (RC / ELRS)

## Setup

### Software

- ELRS configurator/flash tools:
  <https://www.expresslrs.org/quick-start/installing-configurator/>
- ELRS Web UI:
  <https://www.expresslrs.org/quick-start/webui/>
- Flash Arduino if not already flashed (it should show up as joystick device in `/dev/input/js0` or `/dev/input/js1`).

### Hardware

Wired chain:

`Antenna -> Receiver -> Arduino (USB) -> Jetson`

Required settings:

- Baud rate: `115200`
- Binding phrase must match on transmitter and receiver

## Launch

If Arduino is flashed and joystick device appears, use Donkeycar joystick mode from `donkeycar.md`:

```bash
source ~/donkey/bin/activate
cd ~/projects/mycars/path_follower
python manage.py drive --js
```

## Debug

- You may need to power cycle transmitter for first connection.
- If transmitter LED turns solid immediately after plugging in, something is likely wrong (solid red means connected, but connection should not happen instantaneously).

Transmitter LED modes:

- Flashing rapidly: Wi-Fi mode (device accessible via ELRS Web UI)
- Flashing slowly (about once per second): pairing mode (usually around 1 minute)
- Solid red: paired/connected

Input verification options:

- Web tester: <https://hardwaretester.com/gamepad>
- Linux tool:

```bash
jstest /dev/input/js0
```

Use `/dev/input/js1` if multiple joystick devices exist.

### Controller BLE Debug Mode

To debug controller itself in Bluetooth mode:

1. On controller: `SYS > TOOLS > expressLRS > [BLE Joystick]` (use page buttons to navigate pages; use right scroll wheel to scroll/select).
2. On Jetson: open Bluetooth settings and connect to controller.
