# Hacking Lab
## Debian Installation on an Oracle Virtual Box VM
1. Download Oracle Virtual Box which can be done [here](https://www.virtualbox.org/wiki/Downloads).
2. Download the Debian ISO File which can be retrieved from [here](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-12.9.0-amd64-netinst.iso).
3. Create a new virtual machine in Oracle virtual Box by navigating to the menu --> Machine --> New
4. Name the virtual machine and select the ISO image
5. Set the amount of RAM, CPU and storage and finish the process
6. Start the virtual machine
7. Choose in the boot loader the option "Debian GNU/Linux live" and start the instalation process
8. Once the OS is ready test some basic functions such as browser and settings
9. If the tests are good, run the "Install Debian" installer (Calamares)  and go through the wizzard and adjust it to your liking (English language is recommended as online information is in english)
10. For the partition it is best to erase the virtual disk if no specific partitions shall be done
11. Add any additional users if needed and then start the installation
12. Do a snapshot after completion!


# References
Debian ISO Image: https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-12.9.0-amd64-netinst.iso
Oracle Virtual Box download: https://www.virtualbox.org/wiki/Downloads
Installation of virtual machine: https://terokarvinen.com/2021/install-debian-on-virtualbox/

