To use W_Scan

First - ensure that the drivers of the capture card have loaded correctly by inspecting
```
sudo dmesg
```

## Initial Scan
Now we want to run an initial scan by running the command
AN initial scan just tells us which MHz is there signal.  this doesn't acually show the indivdual channels.
```
w_scan -cAU -x > output.txt
```
-cAU == Set country to Australia<br>
-x     generate initial tuning data output for (dvb-)scan instead of VDR channels.conf.

## Using an initial Scan File
-I 	FILE import dvbscan initial_tuning_data
-X  generate zap/czap/xine output instead of VDR channels.conf.

```
w_scan -I output.txt -X > outputX.txt
```