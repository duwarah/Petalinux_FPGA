# Petalinux_FPGA

Install petelinux ubuntu 16 in zybo Z7000 board.
Connect the SD card to the PC using SD card reader and start gparted by

$sudo gparted

If gparted is not installed then run

$sudo apt-get install gparted

Download the required files from
https://drive.google.com/drive/folders/1qn0Ox7mFaWTTCAzqJzZKWqI_l_Tb6m_G?usp=sharing

Follow the steps below to prepare the SD card.

    1. Select the SD card in gparted
    2. Make sure its unmounted and delete the partition of the SD card so that it displays ‘unallocated’ in gparted
    3. Right click the unallocated space and create a new partition with following settings, 
	    Free Space Proceeding (MiB): 4
    	New Size (MiB) : 512, 
	    File System : FAT32, 
	    Label : BOOT. 
    Don’t change other settings and click Add to finish.

    4. Right click the remaining unallocated space and create a new partition with following settings, 
	    Free Space Proceeding (MiB): 0,
	    Free Space Following(MiB): 0, 
	    File System : ext4, 
	    Label : rootfs. 
    Don’t change other settings and click Add to finish.

    5. Apply all changes to create the partitions.
    6. Move all the files in the BOOT folder to BOOT partition of the sd card.
    7. Extract "ubuntu-16.04.2-minimal-armhf-2017-06-18.tar" and move everything to the rootfs directory.
    8. Put the sd card in zybo board, setlect jumper to boot from sd,connect the board to computer using usb  cable and power up the board.
    9. Setup a serial communication in the computer. The baud rate is 115200.
    10. The default username is 'ubuntu' and password is 'temppwd'.
