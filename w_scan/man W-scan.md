```
w_scan -fa -c <COUNTRY_ID> [ options ]
w_scan -fc -c <COUNTRY_ID> [ options ]
w_scan -ft -c <COUNTRY_ID> [ options ]
w_scan -fs -s <SATELLITE_ID> [ options ]
```

## The following options are available.
```
-f TYPE
      Frontend type,
      "a" = ATSC,
      "c" = DVB-C,
      "s" = DVB-S/S2,
      "t" = DVB-T (and ISDB-T) [default]
      Depending on "TYPE", either of the arguments "-s" or "-c" is mandatory.

-c COUNTRY_ID
      Mandatory argument for ATSC scans, cable scans and terrestrian  scans,  see  option
      -f.
      Specifies  the  country  where you try to scan for channels as uppercase two letter
      identifier, e.g.
      DE = Germany,
      US = United States,
      FR = France
      Use "-c?" for a list of all known identifiers.

-s SATELLITE_ID
      Mandatory argument for satellite scans, see option -f.
      Specifies the satellite you wish to scan as uppercase identifier, e.g.
      S19E2 = 19.2° east,
      S13E0 = 13.0° east,
      S0W8 = 0.8° west.
      Use "-s?" for a list of all known identifiers.

-A N   specify ATSC scan type
      1 = terrestrial [default],
      2 = cable,
      3 = both, cable and terrestrial.

-o N   VDR channels.conf format
      2 = VDR-2.0 [default],
      21 = VDR-2.1

-X     generate zap/czap/xine output instead of VDR channels.conf.

-x     generate initial tuning data output for (dvb-)scan instead of VDR channels.conf.

-k     generate channels.dvb for kaffeine instead of VDR channels.conf.

-L     generate VLC xspf playlist (experimental)

-M     mplayer output instead of vdr channels.conf

-G     generate output for Gstreamer dvbsrc plugin

-h     show help

-H     show expert help

```
## expert options
```
       -C CHARSET
              specifies the output charset, i.e. "UTF-8", "ISO-8859-15"
              use 'iconv --list' to see full list of charsets.

       -I FILE
              import dvbscan initial_tuning_data

       -v     verbose (repeat for more)

       -q     quiet (repeat for less)

       -R N   Radio channels
              0 = don't search radio channels
              1 = search radio channels [default]

       -T N   TV channels
              0 = don't search TV channels,
              1 = search TV channels [default]

       -O N   Other services
              0 = don't search other services [default]
              1 = search other services

       -E N   Conditional access / encrypted channels
              0 = only Free TV channels,
              1 = include encrypted channels [default]

       -a N   use device /dev/dvb/adapterN/ [default: auto detect]
              (also allowed: -a /dev/dvb/adapterN/frontendM)
              NOTE: This option is deprecated and should be usually omitted.

       -F     Long filter timeout for reading data from hardware.

       -t N   Tuning timeout, increasing may help if device tunes slowly or has bad reception.
              1 = fastest [default],
              2 = medium,
              3 = slowest

       -i N   spectral inversion setting for cable TV
              0 = off,
              1 = on,
              2 = auto [default]

       -Q     DVB-C modulation [default: choosen by country]
              NOTE: for experienced users only!
              0 = QAM64,
              1 = QAM256,
              2 = QAM128

       -S RATE
              set DVB-C symbol rate, see table: [default: choosen by country]
              NOTE: for experienced users only!!
              0 = 6.9000 MSymbol/s
              1 = 6.8750 MSymbol/s
              2 = 6.9565 MSymbol/s
              3 = 6.9560 MSymbol/s
              4 = 6.9520 MSymbol/s
              5 = 6.9500 MSymbol/s
              6 = 6.7900 MSymbol/s
              7 = 6.8110 MSymbol/s
              8 = 6.2500 MSymbol/s
              9 = 6.1110 MSymbol/s
              10 = 6.0860 MSymbol/s
              11 = 5.9000 MSymbol/s
              12 = 5.4830 MSymbol/s
              13 = 5.2170 MSymbol/s
              14 = 5.1560 MSymbol/s
              15 = 5.0000 MSymbol/s
              16 = 4.0000 MSymbol/s
              17 = 3.4500 MSymbol/s

       -e     extended DVB-C scan flags.
              NOTE: for experienced users only!
              Any combination of these flags:
              1 = use extended symbolrate list,
              2 = extended QAM scan

       -l TYPE
              choose LNB type by name (DVB-S/S2 only) [default: UNIVERSAL],
              "-l?" for list of known LNBs.

       -D Nc  use DiSEqC committed switch position N (N = 0 .. 3)

       -D Nu  use DiSEqC uncommitted switch position N (N = 0 .. 15)

       -p <file>
              use DiSEqC rotor Position file

       -r N   use Rotor position N (N = 1 .. 255)

       -P     ATSC scan: do not use ATSC PSIP tables for scan (PAT and PMT only)
```
#examples
```
       scan satellite 19.2 east:
	      w_scan2 -fs -s S19E2

       scan cable (DVB), Germany:
	      w_scan2 -fc -c DE

       scan aerial (DVB), France:
	      w_scan2 -ft -c FR

       scan cable (ATSC), United States:
	      w_scan2 -fa -A2 -c US

       scan aerial (ATSC), United States:
	      w_scan2 -fa -A1 -c US

       use output format zap/czap/xine:
	      w_scan2 [	OTHER OPTIONS ]	-X

       use output format dvbscan/scan/scan-s2 initial tuning data.
	      w_scan2 [	OTHER OPTIONS ]	-x
	      NOTE: w_scan2 also performs full scans, so there is generally no
	      need for this.
```

