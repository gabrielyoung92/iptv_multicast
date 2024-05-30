Ensure the hardware is working<br>
make a folder for config files

Make w_scan2 and make sure it is available to use in the directory

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
./w_scan2 -I w_scan_transponders.conf -X -t2 > w_scan_channels.conf
```
https://ozdigitaltv.com/transmitters/QLD/165-Mount-Tamborine

We now have the required channels.  but this needs to be separated

## 2) Separate the scanned channels into separate files

The file that is generated is a CSV file using ":" as the delinamtor
0 = Channel name
1 = Frequency (Hz)
2 = Inversion mode
3 = Symbol rate
4 = FEC name, HP
5 = FEC name, LP
6 = Constellation
7 = Transmission mode
8 = Guard interval
9 = Hierarchy information
10 = Video PID
11 = Audio PID
12 = Service ID


Use the bash script to create all the seperate conf files
