# slstatus
slstatus is a status monitor for window managers like dwm. See the official
slstatus web page [here](https://tools.suckless.org/slstatus/). This repository
contains my configuration of slstatus, which can be seen in the config.h file.

## Installation
There are three dependencies: A window manager running on X that uses WM_NAME or
stdin for the status bar, [Font Awesome](fontawesome.com), and pamixer. 
To install slstatus, run the following:
```sh
git clone <url>
cd slstatus
make clean install
```
Running "make" may require root privileges.

## Usage
slstatus can be run from the terminal:
```sh
slstatus
```
Alternatively, it can be added to ~/.xinitrc if the startx command is used to
run the X server.
```sh
echo "slstatus &" >> ~/.xinitrc
```
Then start the X server from a console.
```sh
startx
```

## Configuration
This version of slstatus has been preconfigured to display volume percentage,
CPU utilization percentage, CPU temperature, RAM usage percentage, WiFi signal
strength, day of the week, date, and time. Volume percentage requires ALSA,
which is included in the Linux kernel. Make the following changes to config.h
if necessary: \
For CPU temperature replace the path to your device's sensor file.
For WiFi signal strength replace the network device name with the correct name
for your device. You can list network devices on your computer by running the
following:
```sh
ip link
```
On operating systems using the Linux kernel, the WiFi device usually begins
with a "w" (e.g wlp4s0). \
The following is an image of how this configuration looks in dwm.

![Alt text](slstatus.png?raw=true "slstatus preview")
