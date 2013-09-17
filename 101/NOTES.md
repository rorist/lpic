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

Stage 2 code that let the user choose the partition to load and edit
startup configurations.
IE: LILO, GRUB(2), BOOTMGR, ...

### Chainloading

A boot manager loading an other boot manager, for instance LILO
is loading BOOTMGR (Windows) on an other disk/partition.

Runlevels, shutdown, and reboot
-------------------------------

- man init
- Default run level: grep initdefault /etc/inittab
- Find current runlevel: runlevel
- Changing runlevel: init/telinit
 - init is the first process to be started (pid=1)
 - telinit is a symlink to init
 - init is aware if its invoked from telinit or if it is already running

### Basic runlevels

- 0: Shutdown (or halt) the system
- 1: Single user mode
- 6: Reboot the system

### Halt, reboot and poweroff

poweroff and reboot are symlinks to the halt commands, and produces different results:

- The halt command halt the system
- The poweroff command halt and attempts to power it off
- The reboot command halt and reboots it
