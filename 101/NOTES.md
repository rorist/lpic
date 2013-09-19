System Architecture
===================

Summary
-------

- Basic CLI
- Hardware settings
- Boot the system
- Runlevels

Basic commandline
-----------------

- Explore the filesystem
<pre><code>cd
cd ..
cd /
cd /home/$USER
cd ~
ls
ls -l
ls -la
mv file1 file2
cp file1 file2
rm myile
touch myfile
find .
locate test</code></pre>
- Manipulate files
<pre><code>cat myfile
echo test > myfile
echo test >> myfile</pre></code>
- tab tab

Hardware settings
-----------------

- List hardware devices: lspci, lsusb, lshw
<pre><code>lsusb
lsusb -v -s 001:001
lspci
lspci -v -s 00:00.0
lspci -vv -s 00:00.0
</code></pre>
- Kernel modules: lsmod, modprobe, insmode, rmmode
<pre><code>find /lib/modules/$(uname -r)</code></pre>
 - insmode/rmmode do not resolve modules dependencies, use modprobe!
<pre><code>modprobe module_name
modprobe -r module_name</code></pre>
- Virtual filesystems: /proc /dev /sys
<pre><code>/proc/paritions
/proc/cpuinfo
/proc/cmdline
/proc/meminfo
/proc/net
/proc/dma
/proc/interrupts</code></pre>
<pre><code>/dev/sdX
/dev/hdX
/dev/ttyX
/dev/lpX
/dev/dsp
/dev/usb</code></pre>
<pre><code>/sys/class
/sys/block
/sys/bus</code></pre>


Boot the system
---------------

- BIOS performs self test (POST=Power On Self Test)
 - Checks memory, motherboard components
 - Bips on errors (keyboard not present, etc)
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
