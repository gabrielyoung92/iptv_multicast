Ensure the hardware is working.<br>
make a folder for config files

Make w_scan2 and make sure is available

## 1) Scan for channels using W_SCAN

Do the initial file - This creates just the transponder list.  to make future scanning quicker
```
./w_scan2 -cAU -t2 -x > w_scan_transponders.conf
```

To get everything from the beginning
```
./w_scan2 -cAU -X -t2 > w_scan_channels.conf
```

To use the initial file
```
./w_scan2 -I w_scan_transponders.conf -X -t2 > w_scan_channels_usingInit.conf
```

We now have the required channels.  but this needs to be separated

## 2) Separate the scanned channels into separate files
