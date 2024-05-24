# Firmware

These are firmware files for various tuners that may be required to get the device to work

Checking the output the dmesg will tell if firmware is required
```
sudo dmesg
```

## Firmware Location
Firmware lives in ```/lib/firmware/```<br>

Two options to install:<br>
1 - Copy individual required firmware files into /lib/firmware/ and reboot! 
2 - Install "linux-firmware-hauppauge_0.2.1+xenial_all.deb"  by <br>
``` sudo apt install ./linux-firmware-hauppauge_0.2.1+xenial_all.deb``` and reboot