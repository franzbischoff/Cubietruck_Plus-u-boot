
**This is a simple guide to build uboot for Cubietruck Plus**

# build step:

  ./build.sh -p sun8iw6p1



# update uboot:

After build , You will get uboot binaries, There is two way to update uboot using the build binaries.

* Way 1:

Refer: https://github.com/cubieboard/Cubietruck_Plus-binaries

You need to copy the build binaries to corresponding directory:

  Cubietruck_Plus-u-boot/u-boot-2011.09/boot0_sdcard_sun8iw6p1.bin  --> Cubietruck_Plus-binares/bin/raw/u-boot-spl-sun8iw6p1.bin<br>
  Cubietruck_Plus-u-boot/u-boot-2011.09/u-boot-sun8iw6p1.bin        --> Cubietruck_Plus-binares/bin/raw/u-boot-sun8iw6p1.bin 

* Way 2: (this way is used for assuming you have booting system in Cubietruck Plus)

1. copy the build binaries to Cubietruck Plus system

  Cubietruck_Plus-u-boot/u-boot-2011.09/boot0_sdcard_sun8iw6p1.bin  -->  /root/boot-file/u-boot-spl-sun8iw6p1.bin
  Cubietruck_Plus-u-boot/u-boot-2011.09/u-boot-sun8iw6p1.bin        -->  /root/boot-file/u-boot-sun8iw6p1.bin


2. Update uboot in Cubietruck Plus system

  $ cd /root/boot-file
  
  if you are booting from tfcard, run:<br>
  $ sudo ./update_sys_config.sh tfcard

  if you are booting form emmc, run:<br>
  $ sudo ./update_sys_config.sh emmc

More details see :

https://github.com/cubieboard/Cubietruck_Plus-products/tree/master/cb5/cb5-linaro-desktop-hdmi/overlay/root/boot-file
https://github.com/cubieboard/Cubietruck_Plus-products/blob/master/cb5/cb5-linaro-desktop-hdmi/overlay/root/boot-file/update_sys_config.sh

