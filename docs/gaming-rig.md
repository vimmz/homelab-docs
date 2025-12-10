(base) wim@pop-os:~$ lscpu | grep -E 'Model name|CPU\(s\)|Socket'
CPU(s):                               16
On-line CPU(s) list:                  0-15
Model name:                           AMD Ryzen 7 5700X3D 8-Core Processor
Socket(s):                            1
NUMA node0 CPU(s):                    0-15
(base) wim@pop-os:~$ free -h
               total        used        free      shared  buff/cache   available
Mem:            31Gi       3.7Gi        23Gi       254Mi       4.5Gi        25Gi
Swap:          4.0Gi          0B       4.0Gi
(base) wim@pop-os:~$ lsblk -o NAME,SIZE,TYPE,MOUNTPOINT
NAME            SIZE TYPE  MOUNTPOINT
loop0             4K loop  /snap/bare/5
loop1          63.8M loop  /snap/core20/2582
loop2          63.8M loop  /snap/core20/2599
loop3          66.8M loop  /snap/core24/1006
loop4          66.8M loop  /snap/core24/988
loop5         404.4M loop  /snap/gnome-46-2404/90
loop6          91.7M loop  /snap/gtk-common-themes/1535
loop7         207.4M loop  /snap/mesa-2404/495
loop8         290.8M loop  /snap/mesa-2404/887
loop9            71M loop  /snap/prometheus/86
loop10          3.7M loop  /snap/rocminfo/2
loop11         50.9M loop  /snap/snapd/24505
loop12         50.9M loop  /snap/snapd/24718
sda           931.5G disk  
└─sda1        931.5G part  
sdb           111.8G disk  
├─sdb1          128M part  
├─sdb2        110.7G part  
└─sdb3        867.5M part  
sdc             1.8T disk  
├─sdc1           16M part  
└─sdc2          1.8T part  
zram0             0B disk  
nvme1n1       931.5G disk  
├─nvme1n1p1    1022M part  /boot/efi
├─nvme1n1p2       4G part  /recovery
├─nvme1n1p3       4G part  
│ └─cryptswap     4G crypt [SWAP]
├─nvme1n1p4   372.5G part  /
├─nvme1n1p5      16M part  
├─nvme1n1p6   549.2G part  
└─nvme1n1p7     738M part  
nvme0n1       931.5G disk  
├─nvme0n1p1      16M part  
└─nvme0n1p2   931.5G part  
(base) wim@pop-os:~$ lspci | grep -Ei 'vga|3d'
2d:00.0 VGA compatible controller: Advanced Micro Devices, Inc. [AMD/ATI] Navi 48 [RX 9070/9070 XT] (rev c0)
(base) wim@pop-os:~$ ip addr show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: enp6s0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc fq_codel state DOWN group default qlen 1000
    link/ether 2c:f0:5d:5d:7b:1c brd ff:ff:ff:ff:ff:ff
3: enp42s0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc fq_codel state DOWN group default qlen 1000
    link/ether 2c:f0:5d:5d:7b:1b brd ff:ff:ff:ff:ff:ff
4: wlp5s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
    link/ether 34:c9:3d:eb:32:0a brd ff:ff:ff:ff:ff:ff
    inet 192.168.0.227/24 brd 192.168.0.255 scope global dynamic noprefixroute wlp5s0
       valid_lft 86073sec preferred_lft 86073sec
    inet6 2a02:1810:1d1b:b000:960a:4405:4bc6:cb35/64 scope global temporary dynamic 
       valid_lft 236749sec preferred_lft 63949sec
    inet6 2a02:1810:1d1b:b000:a558:8939:9133:7618/64 scope global dynamic mngtmpaddr noprefixroute 
       valid_lft 236749sec preferred_lft 63949sec
    inet6 fe80::eb77:bce3:59c5:92a0/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
5: wlx6245b4e7a4ef: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default qlen 1000
    link/ether 62:45:b4:e7:a4:ef brd ff:ff:ff:ff:ff:ff
6: docker0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default 
    link/ether 2e:dd:39:41:78:89 brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
(base) wim@pop-os:~$ 
