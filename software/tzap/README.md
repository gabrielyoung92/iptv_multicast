# tzap
https://www.linuxtv.org/wiki/index.php/Zap



## Setup
Installed with the [dvb-apps] package

In the users home directory, make a new folder [.tzap]
```
mkdir .tza]
```

With the channels.conf file that you scanned using something like w_scan, copy it into ~/.tzap

Now we can run the command which is ```tzap <chanel name>```
```
gab@iptv:~/.tzap$ tzap "9HD Gold Coast(Nine Network Australia)"
using '/dev/dvb/adapter0/frontend0' and '/dev/dvb/adapter0/demux0'
reading channels from file '/home/supertech/.tzap/channels.conf'
Version: 5.11    FE_CAN { DVB-T + DVB-T2 + DVB-C (A) }
tuning to 648500000 Hz
video pid 0x0202, audio pid 0x028a
status 00 | signal 0000 | snr 0000 | ber 7d668cac | unc 00007ffd |
status 1f | signal e02a | snr 4185 | ber 7d668cac | unc 00007ffd | FE_HAS_LOCK
status 1f | signal e02a | snr 4185 | ber 7d668cac | unc 00007ffd | FE_HAS_LOCK
status 1f | signal e02a | snr 4185 | ber 7d668cac | unc 00007ffd | FE_HAS_LOCK
status 1f | signal e02a | snr 4185 | ber 7d668cac | unc 00007ffd | FE_HAS_LOCK
status 1f | signal e02a | snr 4185 | ber 7d668cac | unc 00007ffd | FE_HAS_LOCK
```
