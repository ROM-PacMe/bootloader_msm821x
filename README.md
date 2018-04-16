Compiling the LK Android bootloader
--------

1) Get the toolchain and install:
  wget https://sourcery.mentor.com/public/gnu_toolchain/arm-none-linux-gnueabi/arm-2009q1-203-arm-none-linux-gnueabi-i686-pc-linux-gnu.tar.bz2
  sudo tar xvf arm-2009q1-203-arm-none-linux-gnueabi-i686-pc-linux-gnu.tar.bz2 --directory /opt/

2) Compile the bootloader:
  PATH=/opt/arm-2009q1/bin:$PATH TOOLCHAIN_PREFIX=arm-none-linux-gnueabi- PROJECT=msm8610 make EMMC_BOOT=1

3) Get your Lumia into diagnostics mode (turn it on using VOL UP + VOL DOWN + POWER) **if you have your Lumia Unlocked

4) BACKUP EVERY SINGLE FILE FROM THE 150MB PARTITION! (Just to be safe)

5) Replace the image/emmcboot.mbn file with your freshly compiled LK bootloader
  cp <repo dir>/build-msm8610/EMMCBOOT.MBN /media/<mount point>/image2/emmcboot.mbn

6) Unmount the bootloader partition from your PC and pull the phone's battery

7) Turn on, wait a few moments, and plug the phone to the PC

8) Test the fastboot connection:
  fastboot devices
  fastboot getvar version
