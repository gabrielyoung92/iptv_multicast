# Information
The Quad PCI card appears to emulate as a PCI USB hub with 2x dualTuners attached as USB devices<br>
This particular card I purchased off of Amazon  [https://www.amazon.com.au/dp/B01FMO2FIS](https://www.amazon.com.au/dp/B01FMO2FIS)<br>
Manufacturer website [https://www.hauppauge.com/pages/products/data_quadhd.html](https://www.hauppauge.com/pages/products/data_quadhd.html)<br>

## Firmware Required Debian
The card requires firmware files to be in ```/lib/firmware/```<br>
- dvb-demod-si2168-b40-01.fw<br>
- dvb_driver_si2157_rom50.fw

## Hardware
- 1x asmedia ASM3142
	- PCIe to Dual USB3.1 Host controller 
	- https://www.asmedia.com.tw/product/55AYQ83xg4uy6Uj0/0C8YQ4asx4yt2JR4/3142
	- lspci<br>
```
02:00.0 USB controller: ASMedia Technology Inc. ASM2142/ASM3142 USB 3.1 Host Controller
```
- 2x eMPIA EM28274
	- This chip 
	- https://linuxtv.org/wiki/index.php/Em28xx_devices
	- https://linuxtv.org/wiki/index.php/Hauppauge_WinTV-dualHD
	- https://empiatech.com/wp/28xxx-usb-tv/
- 4x Si2168

## /dev/
```
gab@iptv:/dev/dvb$ tree
.
├── adapter0
│   ├── demux0
│   ├── dvr0
│   ├── frontend0
│   └── net0
├── adapter1
│   ├── demux0
│   ├── dvr0
│   ├── frontend0
│   └── net0
├── adapter2
│   ├── demux0
│   ├── dvr0
│   ├── frontend0
│   └── net0
└── adapter3
    ├── demux0
    ├── dvr0
    ├── frontend0
    └── net0

```

## lspci
```
02:00.0 USB controller: ASMedia Technology Inc. ASM2142/ASM3142 USB 3.1 Host Controller
```

## lsusb
```
lsusb -version

Bus 003 Device 003: ID 2040:8265 Hauppauge dualHD
Couldn't open device, some information will be missing
Device Descriptor:
  bLength                18
  bDescriptorType         1
  bcdUSB               2.00
  bDeviceClass            0
  bDeviceSubClass         0
  bDeviceProtocol         0
  bMaxPacketSize0        64
  idVendor           0x2040 Hauppauge
  idProduct          0x8265
  bcdDevice            1.00
  iManufacturer           3 HCW
  iProduct                1 dualHD
  iSerial                 2 0014218853
  bNumConfigurations      1
  Configuration Descriptor:
    bLength                 9
    bDescriptorType         2
    wTotalLength       0x0037
    bNumInterfaces          1
    bConfigurationValue     1
    iConfiguration          0
    bmAttributes         0x80
      (Bus Powered)
    MaxPower              500mA
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        0
      bAlternateSetting       0
      bNumEndpoints           2
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      0
      bInterfaceProtocol      0
      iInterface              0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x84  EP 4 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x85  EP 5 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        0
      bAlternateSetting       1
      bNumEndpoints           2
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      0
      bInterfaceProtocol      0
      iInterface              0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x84  EP 4 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x85  EP 5 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0

Bus 003 Device 002: ID 2040:8265 Hauppauge dualHD
Couldn't open device, some information will be missing
Device Descriptor:
  bLength                18
  bDescriptorType         1
  bcdUSB               2.00
  bDeviceClass            0
  bDeviceSubClass         0
  bDeviceProtocol         0
  bMaxPacketSize0        64
  idVendor           0x2040 Hauppauge
  idProduct          0x8265
  bcdDevice            1.00
  iManufacturer           3 HCW
  iProduct                1 dualHD
  iSerial                 2 0014218852
  bNumConfigurations      1
  Configuration Descriptor:
    bLength                 9
    bDescriptorType         2
    wTotalLength       0x0037
    bNumInterfaces          1
    bConfigurationValue     1
    iConfiguration          0
    bmAttributes         0x80
      (Bus Powered)
    MaxPower              500mA
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        0
      bAlternateSetting       0
      bNumEndpoints           2
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      0
      bInterfaceProtocol      0
      iInterface              0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x84  EP 4 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x85  EP 5 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        0
      bAlternateSetting       1
      bNumEndpoints           2
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      0
      bInterfaceProtocol      0
      iInterface              0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x84  EP 4 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x85  EP 5 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0

```


# dmesg
```
[    3.763193] em28xx 3-1:1.0: EEPROM ID = 26 00 01 00, EEPROM hash = 0x30e8c74c
[    3.763196] em28xx 3-1:1.0: EEPROM info:
[    3.763197] em28xx 3-1:1.0:  microcode start address = 0x0004, boot configuration = 0x01
[    3.769485] em28xx 3-1:1.0:  AC97 audio (5 sample rates)
[    3.769487] em28xx 3-1:1.0:  500mA max power
[    3.769488] em28xx 3-1:1.0:  Table at offset 0x27, strings=0x0e6a, 0x1888, 0x087e
[    3.828755] em28xx 3-1:1.0: Identified as Hauppauge WinTV-dualHD DVB (card=99)
[    3.835286] tveeprom: Hauppauge model 178100, rev A4I6, serial# 14218852
[    3.835295] tveeprom: tuner model is SiLabs Si2157 (idx 186, type 4)
[    3.835301] tveeprom: TV standards PAL(B/G) NTSC(M) PAL(I) SECAM(L/L') PAL(D/D1/K) ATSC/DVB Digital (eeprom 0xfc)
[    3.835308] tveeprom: audio processor is None (idx 0)
[    3.835311] tveeprom: has no radio, has IR receiver, has no IR transmitter
[    3.835319] em28xx 3-1:1.0: We currently don't support analog TV or stream capture on dual tuners.
[    3.835329] em28xx 3-1:1.0: dvb set to bulk mode.
[    3.892811] em28xx 3-1:1.0: chip ID is em28174
[    5.107132] em28xx 3-1:1.0: EEPROM ID = 26 00 01 00, EEPROM hash = 0x30e8c74c
[    5.107136] em28xx 3-1:1.0: EEPROM info:
[    5.107137] em28xx 3-1:1.0:  microcode start address = 0x0004, boot configuration = 0x01
[    5.113573] em28xx 3-1:1.0:  AC97 audio (5 sample rates)
[    5.113575] em28xx 3-1:1.0:  500mA max power
[    5.113576] em28xx 3-1:1.0:  Table at offset 0x27, strings=0x0e6a, 0x1888, 0x087e
[    5.172783] em28xx 3-1:1.0: Identified as Hauppauge WinTV-dualHD DVB (card=99)
[    5.174360] tveeprom: Hauppauge model 178100, rev A4I6, serial# 14218852
[    5.174361] tveeprom: tuner model is SiLabs Si2157 (idx 186, type 4)
[    5.174363] tveeprom: TV standards PAL(B/G) NTSC(M) PAL(I) SECAM(L/L') PAL(D/D1/K) ATSC/DVB Digital (eeprom 0xfc)
[    5.174364] tveeprom: audio processor is None (idx 0)
[    5.174365] tveeprom: has no radio, has IR receiver, has no IR transmitter
[    5.174367] em28xx 3-1:1.0: dvb ts2 set to bulk mode.
[    5.372721] em28xx 3-2:1.0: New device HCW dualHD @ 480 Mbps (2040:8265, interface 0, class 0)
[    5.372730] em28xx 3-2:1.0: DVB interface 0 found: bulk
[    5.436851] em28xx 3-2:1.0: chip ID is em28174
[    6.269954] rfkill: input handler disabled
[    6.575275] e1000e 0000:00:1f.6 eno1: NIC Link is Up 1000 Mbps Full Duplex, Flow Control: None
[    6.575326] IPv6: ADDRCONF(NETDEV_CHANGE): eno1: link becomes ready
[    6.651415] em28xx 3-2:1.0: EEPROM ID = 26 00 01 00, EEPROM hash = 0x30e8c74c
[    6.651418] em28xx 3-2:1.0: EEPROM info:
[    6.651419] em28xx 3-2:1.0:  microcode start address = 0x0004, boot configuration = 0x01
[    6.658196] em28xx 3-2:1.0:  AC97 audio (5 sample rates)
[    6.658197] em28xx 3-2:1.0:  500mA max power
[    6.658198] em28xx 3-2:1.0:  Table at offset 0x27, strings=0x0e6a, 0x1888, 0x087e
[    6.716760] em28xx 3-2:1.0: Identified as Hauppauge WinTV-dualHD DVB (card=99)
[    6.718342] tveeprom: Hauppauge model 178100, rev A4I6, serial# 14218853
[    6.718344] tveeprom: tuner model is SiLabs Si2157 (idx 186, type 4)
[    6.718345] tveeprom: TV standards PAL(B/G) NTSC(M) PAL(I) SECAM(L/L') PAL(D/D1/K) ATSC/DVB Digital (eeprom 0xfc)
[    6.718347] tveeprom: audio processor is None (idx 0)
[    6.718347] tveeprom: has no radio, has IR receiver, has no IR transmitter
[    6.718349] em28xx 3-2:1.0: We currently don't support analog TV or stream capture on dual tuners.
[    6.718351] em28xx 3-2:1.0: dvb set to bulk mode.
[    6.776884] em28xx 3-2:1.0: chip ID is em28174
[    7.983836] em28xx 3-2:1.0: EEPROM ID = 26 00 01 00, EEPROM hash = 0x30e8c74c
[    7.983849] em28xx 3-2:1.0: EEPROM info:
[    7.983853] em28xx 3-2:1.0:  microcode start address = 0x0004, boot configuration = 0x01
[    7.991064] em28xx 3-2:1.0:  AC97 audio (5 sample rates)
[    7.991073] em28xx 3-2:1.0:  500mA max power
[    7.991077] em28xx 3-2:1.0:  Table at offset 0x27, strings=0x0e6a, 0x1888, 0x087e
[    8.048799] em28xx 3-2:1.0: Identified as Hauppauge WinTV-dualHD DVB (card=99)
[    8.054582] tveeprom: Hauppauge model 178100, rev A4I6, serial# 14218853
[    8.054597] tveeprom: tuner model is SiLabs Si2157 (idx 186, type 4)
[    8.054598] tveeprom: TV standards PAL(B/G) NTSC(M) PAL(I) SECAM(L/L') PAL(D/D1/K) ATSC/DVB Digital (eeprom 0xfc)
[    8.054599] tveeprom: audio processor is None (idx 0)
[    8.054600] tveeprom: has no radio, has IR receiver, has no IR transmitter
[    8.054601] em28xx 3-2:1.0: dvb ts2 set to bulk mode.
[    8.253081] usbcore: registered new interface driver em28xx
[    8.257484] em28xx 3-1:1.0: Binding DVB extension
[    8.263811] i2c i2c-14: Added multiplexed i2c bus 21
[    8.263813] si2168 14-0064: Silicon Labs Si2168-B40 successfully identified
[    8.263815] si2168 14-0064: firmware version: B 4.0.2
[    8.267285] si2157 21-0060: Silicon Labs Si2157 successfully attached
[    8.267295] dvbdev: DVB: registering new adapter (3-1:1.0)
[    8.267297] em28xx 3-1:1.0: DVB: registering adapter 0 frontend 0 (Silicon Labs Si2168)...
[    8.267300] dvbdev: dvb_create_media_entity: media entity 'Silicon Labs Si2168' registered.
[    8.267510] dvbdev: dvb_create_media_entity: media entity 'dvb-demux' registered.
[    8.270911] em28xx 3-1:1.0: DVB extension successfully initialized
[    8.270914] em28xx 3-1:1.0: Binding DVB extension
[    8.274389] i2c i2c-16: Added multiplexed i2c bus 22
[    8.274391] si2168 16-0067: Silicon Labs Si2168-B40 successfully identified
[    8.274393] si2168 16-0067: firmware version: B 4.0.2
[    8.276329] si2157 22-0063: Silicon Labs Si2157 successfully attached
[    8.276337] dvbdev: DVB: registering new adapter (3-1:1.0)
[    8.276339] em28xx 3-1:1.0: DVB: registering adapter 1 frontend 0 (Silicon Labs Si2168)...
[    8.276341] dvbdev: dvb_create_media_entity: media entity 'Silicon Labs Si2168' registered.
[    8.276645] dvbdev: dvb_create_media_entity: media entity 'dvb-demux' registered.
[    8.280890] em28xx 3-1:1.0: DVB extension successfully initialized
[    8.280893] em28xx 3-2:1.0: Binding DVB extension
[    8.284306] i2c i2c-18: Added multiplexed i2c bus 23
[    8.284308] si2168 18-0064: Silicon Labs Si2168-B40 successfully identified
[    8.284310] si2168 18-0064: firmware version: B 4.0.2
[    8.286407] si2157 23-0060: Silicon Labs Si2157 successfully attached
[    8.286419] dvbdev: DVB: registering new adapter (3-2:1.0)
[    8.286421] em28xx 3-2:1.0: DVB: registering adapter 2 frontend 0 (Silicon Labs Si2168)...
[    8.286423] dvbdev: dvb_create_media_entity: media entity 'Silicon Labs Si2168' registered.
[    8.286737] dvbdev: dvb_create_media_entity: media entity 'dvb-demux' registered.
[    8.290234] em28xx 3-2:1.0: DVB extension successfully initialized
[    8.290237] em28xx 3-2:1.0: Binding DVB extension
[    8.293827] i2c i2c-20: Added multiplexed i2c bus 24
[    8.293829] si2168 20-0067: Silicon Labs Si2168-B40 successfully identified
[    8.293831] si2168 20-0067: firmware version: B 4.0.2
[    8.295820] si2157 24-0063: Silicon Labs Si2157 successfully attached
[    8.295832] dvbdev: DVB: registering new adapter (3-2:1.0)
[    8.295833] em28xx 3-2:1.0: DVB: registering adapter 3 frontend 0 (Silicon Labs Si2168)...
[    8.295836] dvbdev: dvb_create_media_entity: media entity 'Silicon Labs Si2168' registered.
[    8.296198] dvbdev: dvb_create_media_entity: media entity 'dvb-demux' registered.
[    8.299724] em28xx 3-2:1.0: DVB extension successfully initialized
[    8.299726] em28xx: Registered (Em28xx dvb Extension) extension
[    8.303356] em28xx 3-1:1.0: Registering input extension
[    8.332818] Registered IR keymap rc-hauppauge
[    8.333402] rc rc0: Hauppauge WinTV-dualHD DVB as /devices/pci0000:00/0000:00:1c.0/0000:02:00.0/usb3/3-1/3-1:1.0/rc/rc0
[    8.333625] rc rc0: lirc_dev: driver em28xx registered at minor = 0, scancode receiver, no transmitter
[    8.333761] input: Hauppauge WinTV-dualHD DVB as /devices/pci0000:00/0000:00:1c.0/0000:02:00.0/usb3/3-1/3-1:1.0/rc/rc0/input14
[    8.333992] em28xx 3-1:1.0: Input extension successfully initialized
[    8.334002] em28xx 3-1:1.0: Remote control support is not available for this card.
[    8.334007] em28xx 3-2:1.0: Registering input extension
[    8.334331] Registered IR keymap rc-hauppauge
[    8.334656] rc rc1: Hauppauge WinTV-dualHD DVB as /devices/pci0000:00/0000:00:1c.0/0000:02:00.0/usb3/3-2/3-2:1.0/rc/rc1
[    8.334805] rc rc1: lirc_dev: driver em28xx registered at minor = 1, scancode receiver, no transmitter
[    8.334923] input: Hauppauge WinTV-dualHD DVB as /devices/pci0000:00/0000:00:1c.0/0000:02:00.0/usb3/3-2/3-2:1.0/rc/rc1/input15
[    8.335072] em28xx 3-2:1.0: Input extension successfully initialized
[    8.335079] em28xx 3-2:1.0: Remote control support is not available for this card.
[    8.335083] em28xx: Registered (Em28xx Input Extension) extension
[   36.326892] si2168 14-0064: firmware: direct-loading firmware dvb-demod-si2168-b40-01.fw
[   36.326907] si2168 14-0064: downloading firmware from file 'dvb-demod-si2168-b40-01.fw'
[   36.540937] si2168 14-0064: firmware version: B 4.0.11
[   36.543974] si2157 21-0060: found a 'Silicon Labs Si2157-A30 ROM 0x50'
[   36.544227] si2157 21-0060: firmware: direct-loading firmware dvb_driver_si2157_rom50.fw
[   36.544230] si2157 21-0060: downloading firmware from file 'dvb_driver_si2157_rom50.fw'
[   37.237715] si2157 21-0060: firmware version: 3.0.5

```