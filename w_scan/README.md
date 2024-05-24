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

This is a slower full scan<br>
w_scan -cAU -t2 -X > outputX.txt
       -t N   Tuning timeout, increasing may help if device tunes slowly or has bad reception.
              1 = fastest [default],
              2 = medium,
              3 = slowest
			  
			  https://ozdigitaltv.com/transmitters/QLD/165-Mount-Tamborine	  



| Affiliation | Callsign   | Frequency       |
| Type        | anything   | here.           |
| Markdown    | is         | neat and cool!  |
| Inner cell  | MD support | is WIP \| soon. |



| **Affiliation	| Callsign	| Frequency	| Power (ERP)	| Pattern	Polarisation**|
|----			|----		|----		
|SBS			|SBS40		|613.500 Mhz|	25.00 kW	|Directional	Horizontal|
|ABC			|ABC41		|620.500 Mhz|	25.00 kW	|Directional	Horizontal|
|Seven			|BTQ42		|627.500 Mhz|	25.00 kW	|Directional	Horizontal|
|Ten			|TVQ44		|641.500 Mhz|	25.00 kW	|Directional	Horizontal|
|Nine			|QTQ45		|648.500 Mhz|	25.00 kW	|Directional	Horizontal|
|Seven			|NEN46		|655.500 Mhz|	25.00 kW	|Directional	Horizontal|
|Nine			|NBN47		|662.500 Mhz|	25.00 kW	|Directional	Horizontal|
|Ten			|NRN48		|669.500 Mhz|	25.00 kW	|Directional	Horizontal|