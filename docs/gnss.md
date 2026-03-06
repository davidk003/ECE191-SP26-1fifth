# GNSS (MosaicX5)

## Setup

### Hardware

- Power via USB-C.
- Connect antennas.
- Linux device path should appear as `/dev/ttyACM<number>`.

Verify device names:

```bash
ls /dev/ttyACM*
```

If the device is `/dev/ttyACM2`, open serial output:

```bash
sudo picocom -b 115200 /dev/ttyACM2
```

Then send one of these GNSS output commands in `picocom`:

- RMC stream:

```text
sno,Stream1,USB2,RMC,sec1
```

- NMEA (GGA) stream:

```text
setNMEAOutput, Stream1, USB2, GGA, sec1
```

You should see output stream immediately.

Exit `picocom` with `Ctrl-A` then `Ctrl-X`.

## Notes for Path Following

- NMEA should work in theory, but path-following did not reliably record on NMEA in prior testing.
- RMC output was used as the working configuration for recording.
- Keep the exact command strings above as-is from the original team notes.

## Launch Context

For path-following workflows, run GNSS after completing Donkeycar setup in `donkeycar.md`.
