# Jetson

Use this page before launching any subsystem. These checks catch most bring-up failures quickly.

## Linux

### Power on and login
When starting up the car with the power button on the power distribution board, the jetson does not startup immediately. You will need to press one of the three buttons on the side of the jetson. (it is either the 1st or 3rd depending on orientation.)

There is a HDMI dummy plug that looks like below that can be used as a power indicator if plugged in, or the fans on the jetson will turn on.

<img width="970" height="728" alt="image" src="https://github.com/user-attachments/assets/6cee9d32-fd1b-492f-920d-5358b168dde6" />

PASSWORD TO JETSON = jetsonucsd

WIFI to use mainly: UCSD robocars

### SSH/remote connectivity
You will use this wifi to ssh or use [nomachine](https://www.nomachine.com/) (A remote desktop software) to access the car. You can hook up a monitor and keyboard to it but it may be annoying to do so every time. We recommend getting used to using a terminal. Use `nano` or `vim` commands on the terminal to edit files. Alternatively, once you have sshed into the car using something like `ssh -X jetson@<ip>` you can setup vscode to access its file system using the "Remote - SSH" extension.

Currently, the IP address is 192.168.11.80, but there is a good chance that this will change due to the router in the lab router having dynamic ip addressing. So in general there are really only 2 easy ways to get the ip address. You can use nomachine and obtain the local ip using `ifconfig` or `ip addr show` to look for the inet ip address which usually has the format `192.168.X.X`. (To speed up searching you can try `ip addr | grep "192"`. The other way is plugging in a monitor directly and using the same commands.

Now you should be able to do:

`ssh -X jetson@<ip>` (-X for x11 server which means any gui that normally needs a display will stream it to your env)

x11 may have problems with mac, im not quite sure what they are though. Regardless, this terminal should be near 1:1 direct access, using rviz2 should even open up a GUI on your computer.


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
