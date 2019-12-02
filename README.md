# hioki3334

A small python code snippet to control HIOKI 3334 AC/DC POWER HiTESTER.

### Setup

Buy USB to RS232/DB9(**Female**) cable and connect HIOKI 3334 to a computer.
Check the USB connection.
Give proper permission to the device.
```
$ lsusb
Bus 001 Device 002: ID 0403:6001 Future Technology Devices International, Ltd FT232 Serial (UART) IC
$ ls -al /dev/ttyUSB*
crw-rw---- 1 root dialout 188, 0 Dec  2 17:21 /dev/ttyUSB0
$ chmod +rw /dev/ttyUSB0 
```

### Usage

```
$ python hioki3334.py -i # init the device
$ python hioki3334.py -r # reset the integration
$ python hioki3334.py -m # ensure the integration was reset
0.000000, 0
$ python hioki3334.py -s # start the integration
$ python hioki3334.py -m # watch the measurement goes up
0.360000, 5
$ python hioki3334.py -m # watch the measurement goes up
0.730000, 10
$ python hioki3334.py -e # stop the integration
```

`-m` prints energy(Wh) and time(s).
