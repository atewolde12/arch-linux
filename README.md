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

- Test that network is working

```shell
ping google.com
```

## Creating partition for bootloader

- Use `lsblk` or `fdisk -l` to list the block devices attached to the VM

**BE SURE TO VERIFY WHICH DEVICE YOU ARE TARGETING**

- After verifying which device you'd like to configure, use `cfdisk` to partion it

For this build, I created a new partion /dev/sda1 and gave it 130M, enough for a bootloader.
```shell
cfidsk /dev/[device]
```


    





