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

## Hardware
### CY7C68013A-56
  
- USB 2.0 Peripheral controller with 16K RAM, 24 GPIOs, 56-pin SSOP for non-battery powered applications
- https://www.infineon.com/cms/en/product/universal-serial-bus/usb-2.0-peripheral-controllers/ez-usb-fx2lp-fx2g2-usb-2.0-peripheral-controller/cy7c68013a-56pvxc/

![](https://raw.githubusercontent.com/gabrielyoung92/iptv_multicast/main/hardware/August%20DVB-T210/github_hardwareRear.jpg)



### Si2168
  
- DVB-T2/T/C Digital TV Demodulator
- https://www.skyworksinc.com/en/Products/TV-and-Video/Si2168-Digital-TV-Demodulators/Si2168
- https://www.linuxtv.org/wiki/index.php/Silicon_Labs_Si2168

![](https://raw.githubusercontent.com/gabrielyoung92/iptv_multicast/main/hardware/August%20DVB-T210/github_hardwareFront.jpg)
   
## /dev/dvb/adaptor#
In this system I already have a quad tuner, so this USB tuner shows as adaptor 4
```
adapter4
├── demux0
├── dvr0
├── frontend0
└── net0
```

## dmesg
```
[ 1743.509337] usb 1-9: new high-speed USB device number 2 using xhci_hcd
[ 1743.658020] usb 1-9: New USB device found, idVendor=0572, idProduct=c68a, bcdDevice= 8.00
[ 1743.658033] usb 1-9: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[ 1743.658040] usb 1-9: Product: EyeTV Stick
[ 1743.658045] usb 1-9: Manufacturer: Geniatech
[ 1743.658050] usb 1-9: SerialNumber: AugustDVBT210.31.07.2023
[ 1743.877322] usb 1-9: dvb_usb_v2: found a 'MyGica Mini DVB-(T/T2/C) USB Stick T230C v2' in warm state
[ 1743.877456] usb 1-9: dvb_usb_v2: will pass the complete MPEG2 transport stream to the software demuxer
[ 1743.877479] dvbdev: DVB: registering new adapter (MyGica Mini DVB-(T/T2/C) USB Stick T230C v2)
[ 1743.877488] usb 1-9: media controller created
[ 1743.878261] dvbdev: dvb_create_media_entity: media entity 'dvb-demux' registered.
[ 1743.891061] i2c i2c-25: Added multiplexed i2c bus 26
[ 1743.891063] si2168 25-0064: Silicon Labs Si2168-D60 successfully identified
[ 1743.891065] si2168 25-0064: firmware version: D 6.0.1
[ 1743.894369] si2157 26-0060: Silicon Labs Si2141 successfully attached
[ 1743.894382] usb 1-9: DVB: registering adapter 4 frontend 0 (Silicon Labs Si2168)...
[ 1743.894385] dvbdev: dvb_create_media_entity: media entity 'Silicon Labs Si2168' registered.
[ 1743.925350] Registered IR keymap rc-total-media-in-hand-02
[ 1743.925444] rc rc2: MyGica Mini DVB-(T/T2/C) USB Stick T230C v2 as /devices/pci0000:00/0000:00:14.0/usb1/1-9/rc/rc2
[ 1743.925686] rc rc2: lirc_dev: driver dvb_usb_dvbsky registered at minor = 2, scancode receiver, no transmitter
[ 1743.925813] input: MyGica Mini DVB-(T/T2/C) USB Stick T230C v2 as /devices/pci0000:00/0000:00:14.0/usb1/1-9/rc/rc2/input16
[ 1743.926046] usb 1-9: dvb_usb_v2: schedule remote query interval to 300 msecs
[ 1743.926058] usb 1-9: dvb_usb_v2: 'MyGica Mini DVB-(T/T2/C) USB Stick T230C v2' successfully initialized and connected
[ 1743.926132] usbcore: registered new interface driver dvb_usb_dvbsky
```


## lsusb
```
Bus 001 Device 002: ID 0572:c68a Conexant Systems (Rockwell), Inc. EyeTV Stick
```

```
Bus 001 Device 002: ID 0572:c68a Conexant Systems (Rockwell), Inc. EyeTV Stick
Couldn't open device, some information will be missing
Device Descriptor:
  bLength                18
  bDescriptorType         1
  bcdUSB               2.00
  bDeviceClass            0
  bDeviceSubClass         0
  bDeviceProtocol         0
  bMaxPacketSize0        64
  idVendor           0x0572 Conexant Systems (Rockwell), Inc.
  idProduct          0xc68a
  bcdDevice            8.00
  iManufacturer           1 Geniatech
  iProduct                2 EyeTV Stick
  iSerial                 3 AugustDVBT210.31.07.2023
  bNumConfigurations      1
  Configuration Descriptor:
    bLength                 9
    bDescriptorType         2
    wTotalLength       0x00e2
    bNumInterfaces          1
    bConfigurationValue     1
    iConfiguration          4
    bmAttributes         0x80
      (Bus Powered)
    MaxPower              500mA
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        0
      bAlternateSetting       0
      bNumEndpoints           4
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      1
      bInterfaceProtocol      1
      iInterface              0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x81  EP 1 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x01  EP 1 OUT
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x82  EP 2 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x86  EP 6 IN
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
      bNumEndpoints           3
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      1
      bInterfaceProtocol      1
      iInterface              0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x81  EP 1 IN
        bmAttributes            3
          Transfer Type            Interrupt
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0040  1x 64 bytes
        bInterval               3
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x01  EP 1 OUT
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x82  EP 2 IN
        bmAttributes            1
          Transfer Type            Isochronous
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x13f2  3x 1010 bytes
        bInterval               1
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        0
      bAlternateSetting       2
      bNumEndpoints           3
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      1
      bInterfaceProtocol      1
      iInterface              0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x81  EP 1 IN
        bmAttributes            3
          Transfer Type            Interrupt
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0040  1x 64 bytes
        bInterval               3
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x01  EP 1 OUT
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x82  EP 2 IN
        bmAttributes            1
          Transfer Type            Isochronous
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x12d6  3x 726 bytes
        bInterval               1
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        0
      bAlternateSetting       3
      bNumEndpoints           3
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      1
      bInterfaceProtocol      1
      iInterface              0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x81  EP 1 IN
        bmAttributes            3
          Transfer Type            Interrupt
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0040  1x 64 bytes
        bInterval               3
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x01  EP 1 OUT
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x82  EP 2 IN
        bmAttributes            1
          Transfer Type            Isochronous
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x12ae  3x 686 bytes
        bInterval               1
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        0
      bAlternateSetting       4
      bNumEndpoints           3
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      1
      bInterfaceProtocol      1
      iInterface              0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x81  EP 1 IN
        bmAttributes            3
          Transfer Type            Interrupt
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0040  1x 64 bytes
        bInterval               3
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x01  EP 1 OUT
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x82  EP 2 IN
        bmAttributes            1
          Transfer Type            Isochronous
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x03ca  1x 970 bytes
        bInterval               1
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        0
      bAlternateSetting       5
      bNumEndpoints           3
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      1
      bInterfaceProtocol      1
      iInterface              0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x81  EP 1 IN
        bmAttributes            3
          Transfer Type            Interrupt
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0040  1x 64 bytes
        bInterval               3
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x01  EP 1 OUT
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x82  EP 2 IN
        bmAttributes            1
          Transfer Type            Isochronous
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x02ac  1x 684 bytes
        bInterval               1
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        0
      bAlternateSetting       6
      bNumEndpoints           3
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      1
      bInterfaceProtocol      1
      iInterface              0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x81  EP 1 IN
        bmAttributes            3
          Transfer Type            Interrupt
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0040  1x 64 bytes
        bInterval               3
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x01  EP 1 OUT
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0200  1x 512 bytes
        bInterval               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x82  EP 2 IN
        bmAttributes            1
          Transfer Type            Isochronous
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x03ac  1x 940 bytes
        bInterval               1
```




