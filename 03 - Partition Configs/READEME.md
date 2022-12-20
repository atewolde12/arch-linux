## 03 - Partition Configs

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
