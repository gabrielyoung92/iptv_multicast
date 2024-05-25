# scan

## Initial scan files
To scan you need to use an initial scan file from what i can see. <br>
The files are located in ```/usr/share/dvb/dvb-t/```  (For DVB-T)

You will need to copy a file which matches your location the best<br>
For example, as I am located on the Gold Coast, Australia, i have 2 options
1. /usr/share/dvb/dvb-t/au-GoldCoast<br>
2. /usr/share/dvb/dvb-t/auto-Australia (My Prefered)

Now that you have located your required file(s), you will need to either remember it's full path, or copy to your user home

## Running scan




scan auto-Australia > scan_output.txt



[ 1917.036081] scan[1437]: segfault at 7 ip 00007fba7713bf19 sp 00007fff720ea608 error 4 in libc.so.6[7fba7700c000+155000] likely on CPU 2 (core 2, socket 0)
