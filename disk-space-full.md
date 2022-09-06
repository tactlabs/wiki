/ [Home](index.md)

# Disk space full
## Problem:
 Unable to boot in Ubuntu (v: 20.04 lts / Focal Fossa) due to Disk Space full

## Solution: 
1. During boot, Choose to start in Advanced mode in Ubuntu
2. Choose the option to start in recovery mode
3. Select the clean command to free up the disk space
4. Reboot the system using the resume command
5. In Ubuntu, open the terminal and run the following commands to free up disk space:
    - ```docker system prune -a```
    - ```sudo apt-get clean```
    - ```sudo apt-get autoremove --purge```
6. Uninstall unnecessary apps
7. Delete unnecessary files
8. Reboot the system
   
---

## Recommended: 
You can also use additional tools like :

 - [BleachBit](https://www.osradar.com/keep-ubuntu-clean-with-bleachbit/)

 - [Stacer](https://linuxconfig.org/how-to-install-stacer-on-ubuntu-20-04-focal-fossa-linux-desktop) 

 - [Ubuntu Cleaner](https://answersdb.com/linux/how-do-i-download-ubuntu-cleaner.html)

