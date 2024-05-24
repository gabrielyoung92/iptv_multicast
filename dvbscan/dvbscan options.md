usage: dvbscan <options> as follows:
-h                     help
-adapter <id>          adapter to use (default 0)
-frontend <id>         frontend to use (default 0)
-demux <id>            demux to use (default 0)
-secfile <filename>    Optional sec.conf file.
-secid <secid> ID of the SEC configuration to use, one of:
                        * UNIVERSAL (default) - Europe, 10800 to 11800 MHz and 11600 to 12700 Mhz,
                                                Dual LO, loband 9750, hiband 10600 MHz.
                        * DBS - Expressvu, North America, 12200 to 12700 MHz, Single LO, 11250 MHz.
                        * STANDARD - 10945 to 11450 Mhz, Single LO, 10000 Mhz.
                        * ENHANCED - Astra, 10700 to 11700 MHz, Single LO, 9750 MHz.
                        * C-BAND - Big Dish, 3700 to 4200 MHz, Single LO, 5150 Mhz.
                        * C-MULTI - Big Dish - Multipoint LNBf, 3700 to 4200 MHz,
                                               Dual LO, H:5150MHz, V:5750MHz.
                        * One of the sec definitions from the secfile if supplied
-satpos <position>     Specify DISEQC switch position for DVB-S.
-inversion <on|off|auto> Specify inversion (default: auto).
-uk-ordering           Use UK DVB-T channel ordering if present.
-timeout <secs>        Specify filter timeout to use (standard specced values will be used by default)
-filter <filter>       Specify service filter, a comma seperated list of the following tokens:
                        (If no filter is supplied, all services will be output)
                        * tv - Output TV channels
                        * radio - Output radio channels
                        * other - Output other channels
                        * encrypted - Output encrypted channels
-out raw <filename>|-   Output in raw format to <filename> or stdout
     channels <filename>|-  Output in channels.conf format to <filename> or stdout.
     vdr12 <filename>|- Output in vdr 1.2.x format to <filename> or stdout.
     vdr13 <filename>|- Output in vdr 1.3.x format to <filename> or stdout.
<initial scan file>