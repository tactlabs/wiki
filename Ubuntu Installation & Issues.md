Ubuntu Installation & Issues

-------------------------------------------------------------------
### Ubuntu Installation

```
 1) Download Ubuntu
 https://ubuntu.com/
 ```
 ```
 2) Download Rufus, SD Card Formatter and EasyBCD
 Rufus - https://rufus.ie/
 SD Card Formatter - https://www.sdcard.org/downloads/formatter/
 EasyBCD - https://www.filecroco.com/download-easybcd/
 ```
 ```
 3) Windows + R and Type msinfo32
 Check BIOS type - Legacy / UEFI
 ```
 ```
 4) Unzip SD Card Formatter and Install the setup
 ```
 ```
 5) Open SD Card Formatter
    Select SD Card / Pendrive
    Click Format
 ```
 ```
 6) Open Rufus

 Legacy -
 
 Device - Select Device (SD Card / Pendrive)
 Boot selection - Select Downloaded Ubuntu ISO image
 Partition scheme - MBR
 Target system - BIOS or UEFI
 
 Keep the remaining as default
 
 Click Start
 
 Select Write in ISO image mode
 
 press OK
 
 a popup will appear, press OK again
 

 UEFI -
 
 Device - Select Device (SD Card / Pendrive)
 Boot selection - Select Downloaded Ubuntu ISO image
 Partition scheme - GPT
 Target system - UEFI (non CSM)
 
 Keep the remaining as default
 
 Click Start
 
 Select Write in ISO image mode
 
 press OK
 
 a popup will appear, press OK again
 ```
 ```
 7) Create Partition

 Press Windows + R 
 
 Enter diskmgmt.msc
 
 Note -

 Create a Separate Partition, Don't Ever Install in C Drive
 
 50GB is Enough For Ubuntu but We Recommend 70GB
```
```
 8) Restart System and Press boot option (F12 / Based on your system)
 ```
 ```
 9) Select USB
 
 This'll take few moments
 ```
 ```
 10) Ubuntu Open

 11) Keyboard Layout

 Left it as Default and Press Continue
 
 12) Wireless
	
 Select I don't want to connect to wifi right now
 
 13) Updates and Other Software

 Select Normal Installation
 
 Uncheck all the Other Options and Press Continue
 
 14) Installation Type


 Select Something Else and Press Continue
 ```
 ```
 1) Click the free space (Unallocated Partition) which we created in Windows
 
 Click + Button, Create Partition Window will popup
 
 Minus 5GB from the free space
 
 For Example - If the free space is 70GB minus 5GB from it and Give 65GB
 
 Size - 65GB (For Example)
 Use as - Ext4 journaling file system
 Mount point - /
 
 2) Click the balance 5GB (Approx) from the free space

 Click + Button, Create Partition Window will popup
 
 Size - Don't Change, Left it as Default
 Use as - swap area

 3) Device for boot loader installation

 Select the Newly Created Partition (65GB)
 
 For Example - /dev/sda4 
 
 Warning - Check whether you're selecting the Right Device or not
 
 Click Install now
 
 A popup will appear, Press Continue
 
 15) Where are you?

 Select India in Map and Cress Continue
 
 16) Who are you?

 Give your Name, Username and Password and Press Continue
 
 This'll take few moments, please wait
 
 17) Installation Complete

 Now, Restart your Computer and Remove the USB
 
 18) Select Ubuntu in GRUB Boot Loader
 
 19) Login by Entering your Password

 20) Press Next, Next, Next..
 
 21) That's it You've Installed Ubuntu in your System. Congrats!
 ```

 ```
 
### Issues

1) Access to Disk Manager Is Denied.

* Run Command Prompt as Administrator
* diskmgmt.msc

HP Pavilion Boot Menu

Esc + F9


2) RST Enabled

Reference - https://discourse.ubuntu.com/t/ubuntu-installation-on-computers-with-intel-r-rst-enabled/15347

* Run Command Prompt as Administrator
* bcdedit /set {current} safeboot minimal
* Install Ubuntu
* Restart
* Open Command Prompt in Recovery Mode
* bcdedit /deletevalue {current} safeboot
* Restart


3) Grub Not Showing

Reference - https://itsfoss.com/no-grub-windows-linux/

* Run Command Prompt as Administrator
* bcdedit /set {bootmgr} path \EFI\ubuntu\grubx64.efi
* Restart

Not Working, Try below Commands

* bcdedit /deletevalue {bootmgr} path \EFI\ubuntu\grubx64.efi
* bcdedit /set {bootmgr} path \EFI\Microsoft\Boot\bootmgfw.efi



-------------------------------------------------------------------
```