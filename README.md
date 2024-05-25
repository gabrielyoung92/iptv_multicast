# iptv_multicast
This is my work on multicast IPTV for a project at work using the LR UR series (Digital Signage) TV's<br>

The plan is to receive TV Stations over the air and send out the TS streams over an IPv4/IPv6 network by multicast using Netgear AV Line M4250 network switches
There will also be other sources of video such as unicast video, RTSP, etc

A big source of information has been from Tall Paul Tech's YouTube channel (CWNE88)<br>
https://www.youtube.com/playlist?list=PLGvkW0sr-RWZHi-5XtnWxIjMLhjG8UffL


## Resources
https://github.com/fishscene/TV2MultiCast<br>
https://www.hospitableit.com/howto/streaming-dvb-t-over-an-ip-network-using-mumudvb-on-a-raspberry-pi-3/<br>
https://angrytechnician.wordpress.com/category/technical-articles/iptv/<br>
https://goughlui.com/2013/11/10/project-building-a-dvb-t-tv-tuner-server-with-mumudvb/<br>
https://github.com/braice/MuMuDVB<br>
https://mumudvb.net/documentation/asciidoc/mumudvb-2.1.0/README_CONF.html

## Hardware
[Hardware](https://www.amazon.com.au/dp/B008D8K50Q)
DVB-T210 

dmegs output

Ensure the device is in "Warm State" !!
```
[68295.779704] usb 1-1.2: new high-speed USB device number 7 using dwc_otg
[68295.880469] usb 1-1.2: New USB device found, idVendor=0572, idProduct=c68a, bcdDevice= 8.00
[68295.880488] usb 1-1.2: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[68295.880495] usb 1-1.2: Product: EyeTV Stick
[68295.880500] usb 1-1.2: Manufacturer: Geniatech
[68295.880505] usb 1-1.2: SerialNumber: AugustDVBT210.31.07.2023
[68296.300180] usb 1-1.2: dvb_usb_v2: found a 'MyGica Mini DVB-(T/T2/C) USB Stick T230C v2' in warm state
[68296.300741] usb 1-1.2: dvb_usb_v2: will pass the complete MPEG2 transport stream to the software demuxer
[68296.300824] dvbdev: DVB: registering new adapter (MyGica Mini DVB-(T/T2/C) USB Stick T230C v2)
[68296.300838] usb 1-1.2: media controller created
[68296.301804] dvbdev: dvb_create_media_entity: media entity 'dvb-demux' registered.
[68296.334494] i2c i2c-11: Added multiplexed i2c bus 12
[68296.334519] si2168 11-0064: Silicon Labs Si2168-D60 successfully identified
[68296.334526] si2168 11-0064: firmware version: D 6.0.1
[68296.349849] si2157 12-0060: Silicon Labs Si2141 successfully attached
[68296.349964] usb 1-1.2: DVB: registering adapter 0 frontend 0 (Silicon Labs Si2168)...
[68296.349990] dvbdev: dvb_create_media_entity: media entity 'Silicon Labs Si2168' registered.
[68296.351258] Registered IR keymap rc-total-media-in-hand-02
[68296.351354] rc rc1: MyGica Mini DVB-(T/T2/C) USB Stick T230C v2 as /devices/platform/soc/3f980000.usb/usb1/1-1/1-1.2/rc/rc1
[68296.351479] rc rc1: lirc_dev: driver dvb_usb_dvbsky registered at minor = 0, scancode receiver, no transmitter
[68296.351606] input: MyGica Mini DVB-(T/T2/C) USB Stick T230C v2 as /devices/platform/soc/3f980000.usb/usb1/1-1/1-1.2/rc/rc1/input2
[68296.351809] usb 1-1.2: dvb_usb_v2: schedule remote query interval to 300 msecs
[68296.351822] usb 1-1.2: dvb_usb_v2: 'MyGica Mini DVB-(T/T2/C) USB Stick T230C v2' successfully initialized and connected
[68296.351954] usbcore: registered new interface driver dvb_usb_dvbsky
```

```
[   37.258083] si2157 21-0060: firmware: failed to load dvb_driver_si2157_rom50.fw (-2)
[   37.258118] si2157 21-0060: firmware: failed to load dvb_driver_si2157_rom50.fw (-2)
[   37.258153] si2157 21-0060: firmware: failed to load dvb-tuner-si2157-a30-01.fw (-2)
[   37.258181] si2157 21-0060: firmware: failed to load dvb-tuner-si2157-a30-01.fw (-2)
```

https://launchpad.net/~b-rad/+archive/ubuntu/kernel+mediatree+hauppauge


### install .deb file
sudo apt install ./<filename>


device
```
/dev/dvb/adapter0 
```

## Software Install
Install all updates, and install needed applications:


Make sure computer is fully up-to-date.
```
sudo apt-get update && sudo apt-get upgrade -y
````

Install required software
```
sudo apt-get install dvb-apps dvblast -y
sudo apt-get install dtv-scan-tables dvb-apps dvbtune w-scan libdvbcsa1

wget http://ftp.au.debian.org/debian/pool/main/m/mumudvb/mumudvb_1.7.1-1+b1_amd64.deb
sudo dpkg -i mumudvb_1.7.1-1+b1_amd64.deb

```

There are 2 methods to scan.  one is to use "scan"  the other is to use "dvbscan"

## "scan"
First we need to get a pre-defined list of frequencies found in
```
cd /usr/share/dvb/dvb-legacy/dvb-t
```
Perform a 'ls' to show all areas.  Find your local file such as 'au-GoldCoast'

The contents of this file will output (As at 2024-05-08
```
T 585500000 7MHz 2/3 NONE QAM64 8k 1/8 NONE
T 704500000 7MHz 3/4 NONE QAM64 8k 1/8 NONE
T 809500000 7MHz 3/4 NONE QAM64 8k 1/16 NONE
T 788500000 7MHz 3/4 NONE QAM64 8k 1/16 NONE
T 634500000 7MHz 3/4 NONE QAM64 8k 1/16 NONE
T 746500000 7MHz 3/4 NONE QAM64 8k 1/16 NONE
T 725500000 7MHz 3/4 NONE QAM64 8k 1/16 NONE
```

We now need to copy the required file into home directory so that we can use it to scan
```
cd au-GoldCoast ~
cd ~
```

or if you're in the home directory already
```
cp /usr/share/dvb/dvb-legacy/dvb-t/au-GoldCoast .
```

Now we scan for TV using the file copied
```
scan au-GoldCoast > output.txt
```

Outputting to the terminal isn't useful (but we can see if it is working).  Now let's output to a file
```
scan au-GoldCoast > output.txt
```


## Method 2 - "dvbscan"


Now that the required software is installed we need to create a directory to store the output of scanning.  This will create 'dvblast' in the users home directory
```
mkdir ~/dvblast
```

We now need to scan for TV channels.   TO know the input commands 'man -h'







sudo w_scan -X -c US > ~/dvblast/channels.txt
nano ~/dvblast/channels.txt


w_scan -f t -c AU -X -v -R 1 -T 1 -O 1 -E 0 -t 2 > channels_advanced.conf

w_scan -ft -CAU -x > output.txt


# IGMP snooping on edge max switch
enabling IGMP snooping will break IPv6.  need to enable MLD.  can only do this through CLI<be>
as per https://community.ui.com/questions/How-to-set-up-MLD-snooping-on-EdgeSwitch/9ed69bf6-2751-4585-9af3-f11e8aefea96

```
ssh into EdgeSwitch

# enable privilage mode
enable

# enable global config mode
configure

# enbale MLD snooping globally
set mld

# enanle MLD snooping on all the switch ports
set mld interfacemode

# exit global config mode
exit

# enable vlan mode
vlan database

# enable MLD snooping on vlan 101
set mld 101

# exit vlan mode
exit

# enable global config mode
configure

# enter port config mode
interface 0/4

# specify multicast router port as port 0/4 on vlan 101
set mld mrouter interface
set mld mrouter 101

# exit port config mode
exit

# exit global config mode
exit

# exit privilage mode
exit

# save config
write memory

# commands to check MLD snooping status
show mld
show mldsnooping mrouter interface 0/4
show mldsnooping mrouter vlan 101
```
