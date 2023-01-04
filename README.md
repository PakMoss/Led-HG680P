# Led-HG680P / s905x-gpio
Led Indicator Internet HG680P 
GPIO controller for Amlogic S905X devices

## Instalation
- choose your s905x device model, example for model ```hg680p```
- install gpio controller to system
```sh
(cd /usr/bin && curl -sLko hgledon.sh https://raw.githubusercontent.com/PakMoss/Led-HG680P/main/hgledon.sh && chmod +x hgledon.sh)
```
- run ```device_model.sh``` script to show help menu
```sh
hgledon.sh
```
output:
```sh
Usage:
  -power  [on, off, warn, dis]
  -lan    [on, off, warn, dis]
  -usb    [reset]
```

## Resetting USB Devices
- some s905x gpio controller contains feature to reset USB device such as ```hg680p```
- to reset USB devices, simply type command:
```sh
hgledon.sh -usb reset
```

## Instalation on OpenWRT
- Copy file hgled & hgledon
- Paste the two files into the folder usr/bin
- and change the permission to 0755
- and edit the files in the folder etc/ & file name rc.local
- edit the rc.local file in and paste this text above exit 0
```sh
sleep 20 && /usr/bin/hgled -r
```
