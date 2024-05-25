# dvblast

```
apt install dvblast
```

## Config file
Using the channels.conf file generate by w_scan (or others) 



```
gab@iptv:~/.tzap$ dvblast
DVBlast 3.4 (release)
Usage: dvblast [-q] [-c <config file>] [-r <remote socket>] [-t <ttl>] [-o <SSRC IP>] [-i <RT priority>] [-A <ASI adapter>][-a <adapter>] [-n <frontend number>] [-S <diseqc>] [-k <uncommitted port>][-f <frequency>][-s <symbol rate>] [-v <0|13|18>] [-p] [-b <bandwidth>] [-I <inversion>] [-F <fec inner>] [-m <modulation] [-R <rolloff>] [-P <pilot>] [-K <fec lp>] [-G <guard interval>] [-H <hierarchy>] [-X <transmission>] [-O <lock timeout>] [-D [<src host>[:<src port>]@]<src mcast>[:<port>][/<opts>]*] [-u] [-w] [-U] [-L <latency>] [-E <retention>] [-d <dest IP>[<:port>][/<opts>]*] [-3] [-z] [-C [-e] [-M <network name>] [-N <network ID>]] [-T] [-j <system charset>] [-W] [-Y] [-l] [-g <logger ident>] [-Z <mrtg file>] [-V] [-h] [-B <provider_name>] [-1 <mis_id>] [-2 <size>] [-5 <DVBS|DVBS2|DVBC_ANNEX_A|DVBC_ANNEX_B|DVBT|DVBT2|ATSC|ISDBT>] -y <ca_dev_number> [-J <DVB charset>] [-Q <quit timeout>] [-0 pid_mapping] [-x <text|xml>][-6 <print period>] [-7 <ES timeout>]
Input:
  -A --asi-adapter      read packets from an ASI adapter (0-n)
  -a --adapter          read packets from a Linux-DVB adapter (typically 0-n)
  -b --bandwidth        frontend bandwidth
  -D --rtp-input        read packets from a multicast address instead of a DVB card
  -5 --delsys           delivery system
    DVBS|DVBS2|DVBC_ANNEX_A|DVBT|DVBT2|ATSC|ISDBT|DVBC_ANNEX_B(ATSC-C/QAMB) (default guessed)
  -f --frequency        frontend frequency
  -8 --lnb-type <type>  Set LNB type')
        universal old-sky (default: universal)
  -9 --dvb-plp-id <number> Switch PLP of the DVB-T2 transmission (default: 0)
  -F --fec-inner        Forward Error Correction (FEC Inner)
    DVB-S2 0|12|23|34|35|56|78|89|910|999 (default auto: 999)
  -I --inversion        Inversion (-1 auto, 0 off, 1 on)
  -m --modulation       Modulation type
    DVB-C  qpsk|qam_16|qam_32|qam_64|qam_128|qam_256 (default qam_auto)
    DVB-T  qam_16|qam_32|qam_64|qam_128|qam_256 (default qam_auto)
    DVB-S2 qpsk|psk_8|apsk_16|apsk_32 (default legacy DVB-S)
  -n --frontend-number <frontend number>
  -p --force-pulse      force 22kHz pulses for high-band selection (DVB-S)
  -P --pilot            DVB-S2 Pilot (-1 auto, 0 off, 1 on)
  -R --rolloff          DVB-S2 Rolloff value
    DVB-S2 35=0.35|25=0.25|20=0.20|0=AUTO (default: 35)
  -1 --multistream-id   Set stream ID (0-2147483648, default: 0).
     --multistream-id-pls-mode   Set multistream PLS mode (ROOT, GOLD, COMBO, default: ROOT)
     --multistream-id-pls-code   Set multistream PLS code (0-262143, default: 0)
     --multistream-id-is-id      Set multistream IS id (0-255, default: 0)
  -K --fec-lp           DVB-T low priority FEC (default auto)
  -G --guard            DVB-T guard interval
    DVB-T  32 (1/32)|16 (1/16)|8 (1/8)|4 (1/4)|-1 (auto, default)
  -H --hierarchy        DVB-T hierarchy (0, 1, 2, 4 or -1 auto, default)
  -X --transmission     DVB-T transmission (2, 4, 8 or -1 auto, default)
  -s --symbol-rate
  -S --diseqc           satellite number for diseqc (0: no diseqc, 1-4, A or B)
  -k --uncommitted      port number for uncommitted DiSEqC switch (0: no uncommitted DiSEqC switch, 1-16)
  -u --budget-mode      turn on budget mode (no hardware PID filtering)
  -v --voltage          voltage to apply to the LNB (QPSK)
  -w --select-pmts      set a PID filter on all PMTs (auto on, when config file is used)
  -O --lock-timeout     timeout for the lock operation (in ms)
  -y --ca-number <ca_device_number>
  -2 --dvr-buf-size <size> set the size of the DVR TS buffer in bytes (default: 7700480)
Output:
  -c --config-file <config file>
  -C --dvb-compliance   pass through or build the mandatory DVB tables
  -d --duplicate        duplicate all received packets to a given destination
  -3 --passthrough      duplicate all received packets to stdout
  -W --emm-passthrough  pass through EMM data (CA system data)
  -Y --ecm-passthrough  pass through ECM data (CA program data)
  -e --epg-passthrough  pass through DVB EIT schedule tables
  -E --retention        maximum retention allowed between input and output (default: 40 ms)
  -L --latency          maximum latency allowed between input and output (default: 100 ms)
  -M --network-name     DVB network name to declare in the NIT
  -N --network-id       DVB network ID to declare in the NIT
  -B --provider-name    Service provider name to declare in the SDT
  -o --rtp-output <SSRC IP>
  -t --ttl <ttl>        TTL of the output stream
  -T --unique-ts-id     generate random unique TS ID for each output
  -U --udp              use raw UDP rather than RTP (required by some IPTV set top boxes)
  -z --any-type         pass through all ESs from the PMT, of any type
  -0 --pidmap <pmt_pid,audio_pid,video_pid,spu_pid>
Misc:
  -h --help             display this full help
  -i --priority <RT priority>
  -j --system-charset   character set used for printing messages (default UTF-8//IGNORE)
  -J --dvb-charset      character set used in output DVB tables (default UTF-8//IGNORE)
  -l --logger           use syslog for logging messages instead of stderr
  -g --logger-ident     program name that will be used in syslog messages
  -x --print            print interesting events on stdout in a given format
  -q --quiet            be quiet (less verbosity, repeat or use number for even quieter)
  -Q --quit-timeout     when locked, quit after this delay (in ms), or after the first lock timeout
  -6 --print-period     periodicity at which we print bitrate and errors (in ms)
  -7 --es-timeout       time of inactivy before which a PID is reported down (in ms)
  -r --remote-socket <remote socket>
  -Z --mrtg-file <file> Log input packets and errors into mrtg-file
  -V --version          only display the version

```