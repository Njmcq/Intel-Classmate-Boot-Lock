# Intel Classmate Boot Lock Documentation

Upon getting my hands on an ASI classmate netbook (an Australian-based company) recently, I was disappointed to find out that I could not freely boot the device due to the below lock system:

![](https://github.com/Njmcq/Intel-Classmate-Boot-Lock/blob/8bfc5ed01a7a4b84f59f639866305d4c8801a3ef/Assets/boot-lock-message.jpg)

This is an interesting security method. Basically, these computers were built for education distribution when they were initially released. In order to prevent theft, manufacturers would permanently install a hardware module and proprietary software. They called it the *Intel Theft Deterrent Application*. This device would require regular connection to the school's Theft Deterrent server, in order to authenticate that it was not stolen. If this message ever appeared, the administrator would either renew the certificate from a server-side application (which was linked to the locked computer), or place a file called tcopp.bin onto a USB stick and manually authenticate using the .bin file. Each .bin would be uniquely generated for the individual device, so only the education institution would have had access to the unlock code.

This lock is tied to the BIOS, and not the Windows or Linux installation. Basically, if you get this lock, you are screwed. But thankfully, there is a temporary solution!

In order to temporarily bypass the screen, you can press **CTRL-INSERT-F11** when you see the error screen. It will get you to a screen that may look something like this:

![Boot menu - select Enter Setup](https://github.com/Njmcq/Intel-Classmate-Boot-Lock/blob/8bfc5ed01a7a4b84f59f639866305d4c8801a3ef/Assets/boot-selection.jpg)

Once you get to this screen (or something like it), you can Enter Setup. From there, it will take you to the BIOS setup menu. Change the date from whatever it currently is to the year **2000**.

![BIOS menu - you'll need to set the system time to the year 2000](https://github.com/Njmcq/Intel-Classmate-Boot-Lock/blob/8bfc5ed01a7a4b84f59f639866305d4c8801a3ef/Assets/change-bios-year.jpg)

Press F10 to save the changes and exit the BIOS setup. Hopefully then, the computer will boot into the OS.

Keep in mind that this solution requires the device to be disconnected from the internet. I installed Windows 7 onto my device and disabled the WiFi card in Device Manager, and kept the system time in the year 2000. I also turned off Internet Sync for the time, just to be sure. Any programs or files which I needed on the computer, I just transfer via USB from one PC to another.

The boot selection menu also serves as the way to flash the tcopp.bin file to the device. Simply insert the FAT32-formatted USB with the file in the root directory into the device, and select the USB drive from the boot menu. If correctly detected, the device will display green text indicating that the process was successful.

I am yet to find a more permanent solution to this issue. It makes reusing these old machines extremely difficult, and with the scarce amount of information online, almost impossible to solve. I hope that this repository will help others who may have the same issue with their device. ASI Solutions (the manufacturer) could not help me and others have had similar experiences when contacting Intel, since they discontinued the Theft Deterrent program years ago and left these computers to die out.

As of early-2023, I decided that this endeavour was no longer a worthwhile mission. [Linked here is an Internet Archive page](https://archive.org/details/intel-theft-deterrent-collection-of-resources) which has a collection of resources that have been very hard to track down, so I think it's useful to have them in one convenient location. For copyright reasons, I am unable to upload them to the repository, but at least they are accessible.

> **Note**
>
> In order to use the Theft Deterrent applications, you must be running Windows Server 2008 R2 on a x64 machine. I tried Win7 x64 as suggested in the forum post but it didn't work. Someone commented in that forum with this same hint, but I thought it best to warn anyone prior to starting on an adventure. Additionally, the VirtualBox VM must also be the same Windows version. You can find working ISOs of Windows Server 2008 on the Internet Archive.

[Original Reddit post here](https://www.reddit.com/r/netbooks/comments/m4rerx/intel_classmate_boot_certificate_expired_how_to/)
