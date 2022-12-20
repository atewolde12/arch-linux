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

For this build, I created a new GPT partion /dev/sda1 and gave it 130M, enough for a bootloader. Type is Linux Filesystem. /dev/sda2 was configured the same, and it has the rest of the memory

```shell
cfidsk /dev/[device]
```

- Mount the partions

This mounts the root partition (one with most space) to /mnt
```shell
mount /dev/sda2 /mnt
```

This creates a directory in /mnt, and then mounts the boot loader to it
```shell
mkdir /mnt/boot
mount /dev/sda1 /mnt/boot
```

- Finally run `pacstrap /mnt [OPTIONS]` to configure the root mount points with some essential packages. This is a very streamlined way of doing things, so I decided to take a clone to try the hard way next time.

```shell
pacstrap /mnt base base-devel linux linux-firmware vim
```

    





