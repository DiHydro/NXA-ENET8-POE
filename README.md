# NXA-ENET8-POE
This is my effort to cross flash the AMX NXA-ENET8-POE to the ECS2100-10P OEM firmware.
NXA-ENET8-POE_V1.1.2.5.bix is the current running firmware. The board has a ROM chip with this version printed on the sticker. ECS2100_Jump.V117.8.8.1.bix is a 
special file, because the location of some memory supposedly changed in later versions. ECS2100_Special2_1.2.2.0_0731.bix is the next "mainline" firmware after the 
"Jump". Then ECS2100_C1.2.2.31.bix is the final and latest firmware that I am trying to get running as the end result.

![14 pin header](https://user-images.githubusercontent.com/3343777/129288130-54c221f1-dba2-4c39-82bd-5406c077e698.png)
In this picture you can see highlighted in red, a 14 pin header which I believe to a debug header. In orange is the ROM with the current version marked on it.

binwalk_V1.1.2.5.txt is the output from binwalk on the current firmware. From it, we can see that there is a uImage header pointing to uBoot as the boot loader. Also we
know that it is running Linux 2.6.19 on a MIPS processor. The squashfs file system is extractable, and binwalk is able to do so. Looking through, it has a lot of the
webserver code that allows for the management of the device. I have tried looking thoruogh this JS and .htm to see if that is were the verification takes place, but I am
not very well versed to know if it's significant or not on the JS side.
