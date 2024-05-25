# Information
This is a single USB DVB-T tuner<>
I purchased multiple of these from amazon https://www.amazon.com.au/dp/B008D8K50Q

## Firmware Required Debian


```
[   37.258083] si2157 21-0060: firmware: failed to load dvb_driver_si2157_rom50.fw (-2)
[   37.258118] si2157 21-0060: firmware: failed to load dvb_driver_si2157_rom50.fw (-2)
[   37.258153] si2157 21-0060: firmware: failed to load dvb-tuner-si2157-a30-01.fw (-2)
[   37.258181] si2157 21-0060: firmware: failed to load dvb-tuner-si2157-a30-01.fw (-2)
```


## dmesg
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