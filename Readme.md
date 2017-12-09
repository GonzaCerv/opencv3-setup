## Raspberry Pi Menu Driven OpenCV 3.2.0 Compile from Source Script
#### Whiptail menu enabled script to help compile opencv3 from source  

### Introduction
This Bash script uses a whiptail menu to assist users who want to compile opencv 3.2.0 from source.
It will update/upgrade Raspberry Pi, Install build dependencies, download source and unzip, perform
a cmake, compile source, make install and optional cleanup.  
Users will be prompted to review output for errors and elect to continue.  They can also repeat a
particular step from the menu if required

### How to Install

#### Quick Install   
Easy Install of opencv3-setup onto a Raspberry Pi Computer with Recent Raspbian Jessie Build.
This is a whiptail menu system that allows install of opencv 3.2.0

    curl -L https://raw.github.com/pageauc/opencv3-setup/master/setup.sh | bash

From a computer logged into the RPI via ssh (Putty) session use mouse to highlight command above, right click, copy.  
Then select ssh(Putty) window, mouse right click, paste.  The command should 
download the install menu script.

#### Manual Install   
From logged in RPI SSH session or console terminal perform the following.

    wget https://raw.github.com/pageauc/opencv3-setup/master/setup.sh
    chmod +x setup.sh
    ./setup.sh

### How to Run Menu

A temporary working folder will be created to store the downloaded opencv
and source,build files. The Default location is /home/pi/tmp_cv3.  If there is limited space
on the Raspbian SD card you may want to create a symoblic link to an external drive
or memory stick.  Then edit(nano) opencv3-setup.sh and change the install_dir
variable to point to the symbolic link for the external storage device. 

Sample commands to use an external ntfs usb hard drive.

    cd ~
    sudo apt-get install ntfs-3g   # Make sure ntfs support installed
    sudo fdisk -l     # will list drive if installed
    mkdir mnt
    sudo mount -t ntfs-3g /dev/sda1 /home/pi/mnt
    mkdir /home/pi/mnt/tmp_cv3
    ln -s /home/pi/mnt/tmp_cv3 tmp_cv3

To Run the whiptail menu setup script.  From a logged in ssh or terminal session run

    cd ~/opencv3-setup
    ./cv32-setup.sh    

Select Menu items in order. You will be asked to review output logs for success before proceeding to next step.
You may be asked to reboot at certain steps. After a Reboot login and run cv32-setup.sh again 
and proceed to next menu item 

This install is based on https://github.com/Tes3awy/OpenCV-3.2.0-Compiling-on-Raspberry-Pi    

Note due to system security, there are some configuration steps that must be done manually using nano.
Please review Step 14 on link above for further instructions.
 
### Prerequisites

* RPI Connection to Internet    
* Reasonably Recent Jessie Full Operating System Installed   
* Sufficient Free Disk Space > 3 GB  df -h to check. To Free disk space see [How to Free Space on Raspbian](http://raspi.tv/2016/how-to-free-up-some-space-on-your-raspbian-sd-card-remove-wolfram-libreoffice)  
* Determine if RPI is a Quadcore cpu  cat /proc/cpuinfo        
* Basic knowledge of unix terminal commands   
* Patience since this will take a few hours    
 
Have Fun   
Claude Pageau    
YouTube Channel https://www.youtube.com/user/pageaucp   
GitHub Repo https://github.com/pageauc

