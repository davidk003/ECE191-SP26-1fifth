# Path Following

Path following uses Donkeycar trigger mappings and PID config values.

## Core Controls

- The algorithm workflow uses `RECORD`, `SAVE`, and `ERASE` buttons.
- `RECORD` and `SAVE` button mappings are set in `init_trigger_maps` in `my_joystick.py`.
- `ERASE` button behavior and PID control values are set in `myconfig.py`.
- Run this only after GNSS and RC are validated.

Relevant files:

- `~/projects/mycars/path_follower/my_joystick.py`
- `~/projects/mycars/path_follower/myconfig.py`

## Tuning and Usage Guide

Follow the Donkeycar path-following guide for PID tuning and path record/follow operations:

<https://docs.donkeycar.com/guide/path_follow/path_follow/>
