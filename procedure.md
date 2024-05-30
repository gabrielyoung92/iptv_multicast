Ensure the hardware is working.<br>
make a folder for config files

## 1) Scan for channels using W_SCAN

Do the initial file - This creates just the transponder list.  to make future scanning quicker
```
w_scan -cAU -R1 -t2 -x > w_scan_transponders.conf
```

To get everything from the beginning
```
w_scan -cAU -X -t2 > w_scan_channels.conf
```

To use the initial file
```
w_scan -I w_scan_transponders.conf -X -t2 > w_scan_channels_usingInit.conf
```

We now have the required channels.  but this needs to be separated

## 2) Separate the scanned channels into separate files
