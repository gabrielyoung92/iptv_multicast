```
sudo apt-get update
sudo apt-get install dvb-tools dvbsnoop ffmpeg mplayer
```

Tune to a channel:
Use dvbtune to tune into the desired channel. You will need the frequency, Video PID (VPID), and Audio PID (APID) obtained from your channel scan.

```
dvbtune -f <frequency> -v <vpid> -a <apid> -bw 7
```

dvbtune -f 627500000 -v 1057 -a 1058 -bw 7
ffprobe /dev/dvb/adapter0/dvr0


## Usage Options
```
gab@iptv:/dev/dvb$ dvbtune
Usage: dvbtune [OPTIONS]

Standard options:

-f freq     absolute Frequency (DVB-S in Hz or DVB-T in Hz)
            or L-band Frequency (DVB-S in Hz or DVB-T in Hz)
-p [H,V]    Polarity (DVB-S only)
-s N        Symbol rate (DVB-S or DVB-C)
-v vpid     Decode video PID (full cards only)
-a apid     Decode audio PID (full cards only)
-t ttpid    Decode teletext PID (full cards only)
-pnr N      Tune to Program Number (aka service) N

-i          Dump SI information as XML

Advanced tuning options:

-c [0-3]    Use DVB card #[0-3]
-tone [0|1] 0=22kHz off, 1=22kHz on
-I [0|1|2]  0=Spectrum Inversion off, 1=Spectrum Inversion on, 2=auto
-D [0-4]    DiSEqC command (0=none)

-qam X      DVB-T modulation - 16, 32, 64 (default), 128 or 256
-gi N       DVB-T guard interval 1_N (N=32 (default), 16, 8 or 4)
-cr N       DVB-T code rate. N=AUTO, 1_2, 2_3 (default), 3_4, 5_6, 7_8
-bw N       DVB-T bandwidth (Mhz) - N=6, 7 or 8 (default)
-tm N       DVB-T transmission mode - N=2 (default) or 8
-x          Attempt to auto-find other transponders (experimental - DVB-S only)
-m          Monitor the reception quality
-n dpid     Add network interface and receive MPE on PID dpid

```