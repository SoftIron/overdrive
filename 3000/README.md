![SoftIron](https://cdn-media.softiron.com/images/softiron-logo.svg)

#OverDrive 3000

##FAQs

**Where can I find networking tools like ifconfig and netstat?**

The replacements in SUSE are as follows :

* arp -> ip [-r] neigh 
* ifconfig -> ip a 
* netstat -> ss [-r] 
* route -> ip r

If you want the old tools type this command as root :

```
zypper install net-tools-deprecated 
```

**How do I connect to my Overdrive’s serial console from a Linux or Mac system?**

You will normally connect to your Overdrive’s serial console via a null-modem cable attached to a USB-serial converter.  On a Linux or Mac system, the screen command can be used as a terminal emulator.  A console session may then be initiated with a command such as:

```
# screen /dev/<serial_device> 115200
```

where <serial_device> is the name of the device node associated with your USB-serial converter.  This name will depend on the specific device driver used by your converter.  For example, for some common converters, <serial_device> could be ttyUSB0 or ttyAMA0.

When you are finished with your console session, you can exit the emulator by entering the key sequence <ctrl>-A K.  Information about the screen command can be found by entering:

```
# man screen
```

**How do I connect to my Overdrive’s serial console from a Windows system?**
You will normally connect to your Overdrive’s serial console via a null-modem cable attached to a USB-serial converter.  On a Windows system, the PuTTY program can be used as a terminal emulator.  Information about PuTTY (including a download link) is available at:

http://www.chiark.greenend.org.uk/~sgtatham/putty/

**Which operating system is pre-installed on my Overdrive?**
Your Overdrive comes installed with a recent version of openSUSE Tumbleweed Linux.  Tumbleweed is the SUSE community’s rolling-release distribution.  More information is available at:

https://en.opensuse.org/openSUSE:AArch64

**How do I perform a fresh installation of openSUSE on my Overdrive?**
Installation instructions for Tumbleweed on AArch64 EFI platforms such as Overdrive are available at:

https://en.opensuse.org/HCL:AArch64_EFI

**How do I configure openSUSE on my Overdrive?**
openSUSE systems are configured using SUSE's YaST configuration tool. More information about YaST can be found at:

https://en.opensuse.org/Portal:YaST

Tip: when running YaST from the command line over the serial console, it is best to use screen as the terminal emulator and to start YaST with the TERM environment variable set to “xterm-color”. This can be done by entering the following command:

```
# TERM=xterm-color yast
```

or

```
# export TERM=xterm-color
# yast
```

**Which operating systems are available for my Overdrive?**
Fedora is available at:

https://fedoraproject.org/wiki/Architectures/AArch64

CentOS is available at:

http://mirror.centos.org/altarch/7/isos/aarch64/

openSUSE is available at:

https://en.opensuse.org/HCL:Seattle

**Which networking ports are available on my Overdrive?**
Devices eth0 and eth1 are active.  Eth0 is the bottom Ethernet port on the back of your Overdrive.

There is a third Ethernet port to the right of eth0.  It is not in use at this time.

**The networking- and disk-activity lights on the front of my Overdrive never light up.  Is my unit defective?**
No.  The networking- and disk-activity lights on your Overdrive are not enabled at this time.

**Why does my Overdrive already have an ssh key?**
A side-effect of our installation procedure is that ssh keys are generated when the operating system is written to disk.  If you prefer not to trust these keys, you are certainly encouraged to generate new ones.

**Which SSD storage devices will work with my Overdrive?**
The following SSD storage devices are known to work with Overdrive:

* Samsung 850 Pro, 128GB (MX-7KE128)
* Samsung 850 Evo (Model MZ-75E250)
* Mushkin Eco2, 60GB (MKNSSDEC60GB)
* Crucial M500, 120GB (CT120M500SSD1)

Other SSDs may work, but have not been tested.

**How do I set a static IP address on my Overdrive's management port?**
Overdrive 3000 procedure to set a static IP for the management port:

If the unit is powered up, shut down and unplug the unit.
Connect to the serial console on the rear panel.
Bring up a screen or other terminal.
Plug in the unit.
When the BIOS screen prompt to enter the setup appears, press delete or escape.

[Boot_0.png]

Once in the Setup Utility, the following screen will appear:

[Boot_1.png]

Use the left arrow key to navigate to the Server Management tab.

[Boot_3.png]

Arrow down to the BMC network configuration menu item.

[Boot_4.png]

Press enter to access the BMC network configuration sub menu.

[Boot_5.png]

Change the Configuration Address source to static.

[Boot_6.png]

Enter the static management port IP address, subnet mask and the router information.

[Boot_7.png]