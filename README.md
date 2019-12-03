rtl8822bu for linux
===================

rtl8822bu linux driver for combined abgn/bluetooth device
This is a driver for the wireless part **only**

For the USB3 issue read at the end  

<u>If one USB-ID is missing, please mail me.</u>  

build/load/function tested with v4.19  


Building and install driver
---------------------------

for building type  
`make`  

for load the driver  
`sudo modprobe cfg80211`  
`sudo insmod rtl8822bu.ko`  


You need to install the needed fw with  
`sudo make installfw`  

If you need to crosscompile use  
`ARCH= CROSS_COMPILE= KSRC=`  
while calling `make` i.e.  

`make ARCH="arm" CROSS_COMPILE=armv5tel-softfloat-linux-gnueabi- KSRC=/home/linux-master modules`  

USB3 Mode Issue
---------------
Realtek aka the chipdesigner does some **stupid** idea to switch into USB3 mode via special efuse read/write.  
And this check is changed compare to the rtl8821au/rtl8814au devices  
Will check for this and enable USB3

Please use prefix **rtl8822bu** if you want to mail me  
But please please don't, I have enough to do.  
TIA  

Hans Ulli Kroll <ulli.kroll@googlemail.com>

https://github.com/ulli-kroll/rtl8822bu
