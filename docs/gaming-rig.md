# Host: Gaming rig

**Role:** Desktop / gaming PC with dual boot **Pop!_OS** and **Windows 11 Home**.  
**Location:** LAN client (Wi-Fi `192.168.0.227`), used for gaming, desktop work, and occasional Docker use.

---

## 1. Hardware Summary

| Component | Details |
|----------|---------|
| CPU      | AMD Ryzen 7 5700X3D – 8 cores / 16 threads (`CPU(s): 16`) |
| RAM      | 32 GB (≈31 GiB) |
| GPU      | AMD Radeon RX 9070 XT (16 GB VRAM, high-end RDNA3 GPU) |
| Motherboard | (Custom build – OEM fields not set) |
| Network  | Wi-Fi `wlp5s0` (`192.168.0.227/24`), wired NICs `enp6s0` & `enp42s0` currently unused |
| Virtual / misc | Docker bridge `docker0` at `172.17.0.1/16` |

### 1.1 Physical Storage (Windows view)

From Windows `Get-PhysicalDisk`:

| Drive (Windows name)        | Size      | Type |
|-----------------------------|-----------|------|
| CT1000MX500SSD1             | 1 TB      | SSD  |
| KINGSTON SA2000M81000G      | 1 TB      | SSD (NVMe) |
| Samsung SSD 870 QVO 2TB     | 2 TB      | SSD  |
| Samsung SSD 840 EVO 120GB   | 120 GB    | SSD  |
| KINGSTON SA2000M81000G      | 1 TB      | SSD (second NVMe) |

Total: **~5 TB** SSD storage across 5 drives.

### 1.2 Storage layout (Linux / Pop!_OS view)

From `lsblk -o NAME,SIZE,TYPE,MOUNTPOINT`:

```text
sda           931.5G disk  
└─sda1        931.5G part  

sdb           111.8G disk  
├─sdb1          128M part  
├─sdb2        110.7G part  
└─sdb3        867.5M part  

sdc             1.8T disk  
├─sdc1           16M part  
└─sdc2          1.8T part  

nvme0n1       931.5G disk  
├─nvme0n1p1      16M part  
└─nvme0n1p2   931.5G part  

nvme1n1       931.5G disk  
├─nvme1n1p1    1022M part  /boot/efi
├─nvme1n1p2       4G part  /recovery
├─nvme1n1p3       4G part  
│ └─cryptswap     4G crypt [SWAP]
├─nvme1n1p4   372.5G part  /
├─nvme1n1p5      16M part  
├─nvme1n1p6   549.2G part  
└─nvme1n1p7     738M part  
```
