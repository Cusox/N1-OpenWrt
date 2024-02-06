# N1-OpenWrt

Phicomm N1 with [Lean's LEDE](https://github.com/coolsnowwolf/lede) and [Flippy's Packit](https://github.com/unifreq/openwrt_packit)

Append [small-package](https://github.com/kenzok8/small-package) feed source

## Software

- Adguard Home
- Amlogic
- Auto Reboot
- Diskman
- File Transfer
- MosDNS
- OpenClash
- Tailscale
- Wol Plus
- Zerotier

## Required OpenWrt Options

```
Target System  -> Arm SystemReady (EFI) compliant
Subtarget      -> 64-bit (armv8) machines
Target Profile -> Generic EFI Boot
Target Images  -> tar.gz

OR

Target System  -> QEMU ARM Virtual Machine
Subtarget      -> QEMU ARMv8 Virtual Machine (cortex-a53)
Target Profile -> Default
Target Images  -> tar.gz



Languages -> Perl
             -> perl-http-date
             -> perlbase-file
             -> perlbase-getopt
             -> perlbase-time
             -> perlbase-unicode
             -> perlbase-utf8
          -> Python
             -> Python3-ctypes
             -> Python3-logging
             -> Python3-yaml

Network -> File Transfer -> curl、wget-ssl
        -> Version Control Systems -> git

Utilities -> Compression -> bsdtar、pigz
          -> Disc -> blkid、fdisk、lsblk、parted
          -> Editors -> vim
          -> Filesystem -> attr、btrfs-progs(Build with zstd support)、chattr、dosfstools、
                           e2fsprogs、f2fs-tools、f2fsck、lsattr、mkf2fs、xfs-fsck、xfs-mkfs
          -> Shells -> bash
          -> coremark、coreutils(-> coreutils-base64、coreutils-dd、coreutils-df、coreutils-nohup、
             coreutils-tail、coreutils-timeout、coreutils-touch、coreutils-tr、coreutils-truncate)、
             gawk、getopt、jq、lm-sensors、losetup、pv、tar、uuidgen



(KVM) (optional)
Utilities -> acpid (optional) (kvm)



(Wifi) (optional)
Kernel modules -> Wireless Drivers -> kmod-brcmfmac(SDIO)
                                   -> kmod-brcmutil
                                   -> kmod-cfg80211
                                   -> kmod-mac80211

Network -> WirelessAPD   -> hostapd-common
                         -> wpa-cli
                         -> wpad-basic
        -> iw                 
```

## Tips
The packaged OpenWrt doesn't provide DHCP functionality in dnsmasq-full. So, if you encounter a dnsmasq startup failure, simply comment out all lines in the `/usr/share/dnsmasq/dhcpbogushostname.conf` file

## License

[MIT](https://github.com/lsilencej/N1-OpenWrt/blob/main/LICENSE) © [**lsilencej**](https://blog.lsilencej.com)
