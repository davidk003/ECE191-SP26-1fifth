# VESC

## Wiring Setup

Servo wiring order is important.

- The VESC servo 3-pin connector (`servo`, `5v`, `gnd`) must first go through a power board.
- Match labels on the power board (`servo`, `5v`, `gnd`) so servo power is supplied by the power distribution board, while the VESC provides signal.
- Connect yellow 2-pin power connector (`5v`) from distribution board to power board.
- Use a 3-pin output (`signal`, `5v`, `gnd`) from the power board to the servos.

VESC speed controller connects to Jetson using micro-USB (or equivalent).

## Flashing and Pre-Test

If VESC is not flashed, use VESC Tool:

<https://vesc-project.com/vesc_tool>

Use it to flash and test steering/acceleration before testing with Donkeycar.

## Debug (If Servo Not Responsive)

- IF SERVO IS NOT RESPONSIVE, CHECK CABLING FIRST.
- The steering servo can be very difficult to debug, and the issue is usually cabling.
- Prior issues were resolved by swapping cables and reseating/wiggling connectors.
- Use a multimeter in voltage mode while steering left and right with the controller to trace where the signal stops.
- On this setup, the cable carrying signal into the small green power regulator board for the servos should be approximately `0.17-0.22V` when steering left and approximately `0.25-0.30V` when steering right.
- The output signal from that board to the servos is a common failure point; if it is reading around `0V`, that is a bad sign and is often where the signal dies.
- Use a voltmeter on VESC output between `servo` signal and `gnd/5v` while activating servo in VESC Tool.
- If you flip servo direction in VESC Tool, voltage should swing around approximately `+/-0.5V`.
- If voltage swings correctly, the issue is likely downstream from VESC firmware/controller.
