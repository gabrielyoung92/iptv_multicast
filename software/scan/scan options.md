```
gab@iptv:~$ scan -h
scan: invalid option -- 'h'

usage: scan [options...] [-c | initial-tuning-data-file]
        atsc/dvbscan doesn't do frequency scans, hence it needs initial
        tuning data for at least one transponder/channel.
        -c      scan on currently tuned transponder only
        -v      verbose (repeat for more)
        -q      quiet (repeat for less)
        -a N    use DVB /dev/dvb/adapterN/
        -f N    use DVB /dev/dvb/adapter?/frontendN
        -d N    use DVB /dev/dvb/adapter?/demuxN
        -s N    use DiSEqC switch position N (DVB-S only)
        -i N    spectral inversion setting (0: off, 1: on, 2: auto [default])
        -n      evaluate NIT-other for full network scan (slow!)
        -5      multiply all filter timeouts by factor 5
                for non-DVB-compliant section repitition rates
        -o fmt  output format: 'zap' (default), 'vdr' or 'pids' (default with -c)
        -x N    Conditional Access, (default -1)
                N=0 gets only FTA channels
                N=-1 gets all channels
                N=xxx sets ca field in vdr output to :xxx:
        -t N    Service select, Combined bitfield parameter.
                1 = TV, 2 = Radio, 4 = Other, (default 7)
        -p      for vdr output format: dump provider name
        -e N    VDR version, default 3 for VDR-1.3.x and newer
                value 2 sets NIT and TID to zero
                Vdr version 1.3.x and up implies -p.
        -l lnb-type (DVB-S Only) (use -l help to print types) or
        -l low[,high[,switch]] in Mhz
        -u      UK DVB-T Freeview channel numbering for VDR

        -P do not use ATSC PSIP tables for scanning
            (but only PAT and PMT) (applies for ATSC only)
        -A N    check for ATSC 1=Terrestrial [default], 2=Cable or 3=both
        -U      Uniquely name unknown services
        -C cs   Override default charset for service name/provider (default = ISO-6937)
        -D cs   Output charset (default = UTF-8)
Supported charsets by -C/-D parameters can be obtained via 'iconv -l' command

```