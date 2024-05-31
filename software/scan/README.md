# scan
Please watch the following video(s) by Tall Paul Tech<br>
https://www.youtube.com/watch?v=asmCMmq06R0&list=PLGvkW0sr-RWZHi-5XtnWxIjMLhjG8UffL



## Initial scan files
To scan you need to use an initial scan file from what i can see. <br>
The files are located in ```/usr/share/dvb/dvb-legacy/dvb-t/```  (For DVB-T)

You will need to copy a file which matches your location the best<br>
For example, as I am located on the Gold Coast, Australia, i have 2 options
1. /usr/share/dvb/dvb-legacy/dvb-t/au-GoldCoast<br>
2. /usr/share/dvb/dvb-legacy/dvb-t/auto-Australia (My Prefered)

Now that you have located your required file(s), you will need to either remember it's full path, or copy to your user home

## Running scan

Make sure you are in your home directory
```
cd ~
```

Now run the scan 
```
scan auto-Australia > scan_output.txt
```




