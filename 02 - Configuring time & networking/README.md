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