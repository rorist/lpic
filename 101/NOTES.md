System Architecture
===================

Summary
-------

- Hardware settings
- Boot the system
- Runlevels

Hardware settings
-----------------

- List hardware devices: lspci, lsusb, lshw
- Virtual filesystems: /proc /dev /sys
 - /proc/paritions /proc/cpuinfo /proc/cmdline /proc/meminfo /proc/net /proc/dma /proc/interrupts
 - /dev/sdX /dev/hdX /dev/ttyX /dev/lpX /dev/dsp /dev/usb
 - /sys/class /sys/block /sys/bus


Boot the system
---------------

- BIOS performs self test (POST)
- BIOS loads  and execute the MBR from bootable devices -> Stage 1
- MBR code checks the partition table and look for primary
  partition marked as active and loads the first sector -> Stage 1
- First sector of the partition then loads further block,
  wich loads the operating system itself -> Stage 2

### Boot manager

Stage 2 code that let the user choose the partition to load.
IE: LILO, GRUB(2), BOOTMGR, ...

### Chainloading

A boot manager loading an other boot manager, for instance LILO
is loading BOOTMGR (Windows) on an other disk/partition.

