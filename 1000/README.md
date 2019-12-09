![SoftIron](https://cdn-media.softiron.com/images/softiron-logo.svg)

# OverDrive 1000

## FAQs

**How can I tell which firmware version I am running?**
The version number is stored in the USB device version field. With your OverDrive 1000 connected to a Linux host, run: 

```
lsusb -d 2e02: | grep bcdDevice
```

**How do I flash updated firmware?**
Download a firmware image at https://github.com/SoftIron/overdrive/blob/master/1000/overdrive_1000_firmware-1.02-2017-01-19.tar.gz. Untar the package and follow the instructions in the included README.txt. More information can be found in the OverDrive 1000 manual available at https://github.com/SoftIron/overdrive/blob/master/1000/OD1000_QSGv1.pdf

**Do I need a programmer or any special hardware to flash updated firmware?**
No. The OverDrive 1000's firmware can be flashed over the USB port.

**How do I exit screen?**
Exit screen by pressing Ctrl-A, then K.

**When I run yast, I can't see what's selected.**
If you are using screen as a terminal program, set your terminal type to xterm-color when running yast using the following: 

```
TERM=xterm-color yast
```

**When I press the power button, does it shutdown the machine properly?**
No, pressing the power button powers off the machine immediately. If you care about your data, shutdown the OverDrive 1000 from the software by running "shutdown -h now" as root.

**What is the login?**
By default the username is "root" and the password is "linux". These should be changed immediately upon login for security purposes, especially if the OverDrive 1000 is connected to a network.

**What is the baud rate of the OverDrive 1000 serial console?**
The baud rate is 115200, but it it is set automatically. There is no need to specify it manually.

**I tried to run screen and it just says "[screen is terminating]".**
If you're running from a Linux computer, make sure you have permission to access /dev/ttyACM0. You can run screen using sudo to run it as root or you can install a udev rules file to /etc/udev/rules.d/ which changes the permissions of the OverDrive 1000 serial device.

**How can I connect to my OverDrive 1000 from Windows?**
First download and install the OverDrive 1000 driver at https://github.com/SoftIron/overdrive/blob/master/1000/od1000_installer.zip. This driver will create a virtual COM port which you can open with PuTTY. Please refer to the OverDrive 1000 manual which is available at https://github.com/SoftIron/overdrive/blob/master/1000/OD1000_QSGv1.pdf for detailed instructions regarding the use of PuTTY.
