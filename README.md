# arch-linux
Repository for Arch Linux build for learning



## 01 - Prerequisite

    - Download the ISO from the offical Arch Linux Wiki

    - Verify the intergity of the download from [here](https://archlinux.org/download/)

    - Configure ISO as a VM in VMware Workstation
        - Mark version as 'Other Linux Distro 5.x Kernel'
        - Give 80GB of storage and 2GB of memory


## 02 - Configuring time & networking
    - Boot the Arch VM with the ISO mounted

    - Verify networking is working (on VMs they will work most of the time out of the box)

     Configure NTP, set to **true**

        ```shell
        timedatectl set-ntp true

        timedatectl set-timezone MST 
        ```

    





