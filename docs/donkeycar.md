# Donkeycar

Donkeycar is used to control the car and run the path-following algorithm.

GNSS and RC should be working first (follow `gnss.md` and `remote-controller.md` before this page to reduce runtime errors).

## Setup

```bash
source ~/donkey/bin/activate
cd ~/projects/mycars/path_follower
```

Use `myconfig.py` for configuration (already set for the 1/5 off-road car in the original setup).

File reference: `~/projects/mycars/path_follower/myconfig.py`

## Launch

Web UI only:

```bash
python manage.py drive
```

Web UI link:
<http://ucsd-agx-03.local:8887/drive>

Joystick control mode (two dashes):

```bash
python manage.py drive --js
```
