---
Title: Raspberry Pi LCD
Slug: raspberry-pi-lcd
Date: 2017-03-19 12:39:25
Status: Published
Category: How-To
Tags: [Raspberry Pi]
---
[![raspberry][q1]][1]

### Fix Config.txt
There is a strange bug where the line in this file cannot go beyond a certain length. I have to manually break all parameters into separate line.

/boot/config.txt
```ini
dtoverlay=ads7846
dtparam=cs=1,penirq=17,penirq_pull=2,speed=1000000,swapxy=1,pmax=255
dtparam=xohms=60,xmin=200,xmax=3900,ymin=200,ymax=3900
```
### Test Transformation
The touch screen for y axis is swapped. Reading from [raspberry forum][forum], the configuration is changed from evdev to libinput.
```shell
env DISPLAY=:0 xinput --set-prop 'ADS7846 Touchscreen' 'Coordinate Transformation Matrix' -1 0 1 0 1 0 0 0 1
```

### Make Permanent
/etc/X11/xorg.conf.d/99-calibration.conf
```text
Option "TransformationMatrix" "-1 0 1 0 1 0 0 0 1"
```

### References
https://wiki.ubuntu.com/X/InputCoordinateTransformation
[waveshare wiki](http://www.waveshare.com/wiki/3.5inch_RPi_LCD_(B))
http://www.circuitbasics.com/raspberry-pi-touchscreen-calibration-screen-rotation/

[forum]: https://www.raspberrypi.org/forums/viewtopic.php?f=28&t=172025

[q1]: raspi.jpg
[1]: raspi.jpg (click to enlarge)
