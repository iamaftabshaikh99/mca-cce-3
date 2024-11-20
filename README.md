### **Q1. What is the Linux Kernel? Explain the Versioning System Used in Linux Kernel Releases. What Are the Major Changes in Each Major Release?**

#### **The Linux Kernel**
The **Linux Kernel** is the fundamental part of the Linux operating system. It acts as the bridge between hardware and software, managing resources like CPU, memory, and I/O devices. It also ensures system stability, multitasking, and security.

#### **Core Responsibilities of the Kernel**
1. **Process Management**: Schedules and prioritizes running tasks.
2. **Memory Management**: Allocates memory to processes.
3. **Device Drivers**: Enables communication between hardware and software.
4. **File System Management**: Handles data storage and retrieval.
5. **Networking**: Provides communication capabilities.

---

#### **Versioning System**
The Linux kernel uses a versioning format **X.Y.Z[-extra]**, where:
- **X**: Major version (e.g., `5` for Linux 5.x).
- **Y**: Minor version, used for features and hardware support.
- **Z**: Patch version for bug fixes and minor updates.
- **Extra**: Optional suffix for pre-releases, e.g., `-rc1` (release candidate 1).

Example Version: **5.15.0-rc1**
- Major Version: `5`
- Minor Version: `15`
- Patch Version: `0`
- Release Candidate: `rc1`

#### **Major Changes Across Kernel Versions**
| **Version** | **Year Released** | **Major Changes**                                                                 |
|-------------|-------------------|----------------------------------------------------------------------------------|
| **2.x**     | 1996–2003         | SMP (Symmetric Multi-Processing), USB support, ext2/ext3 file systems.           |
| **3.x**     | 2011–2015         | Ext4 as the default file system, scalability improvements.                       |
| **4.x**     | 2015–2019         | Live kernel patching, eBPF for enhanced performance and monitoring.              |
| **5.x**     | 2019–2023         | WireGuard VPN, improved AMD/Intel GPU drivers, energy efficiency improvements.   |
| **6.x**     | 2023–present      | Enhanced ARM64 and RISC-V support, better memory management.                     |

---

### **Q2. Enlist the Points in the Boot Process of a Linux System Using systemd**

The **boot process** is the sequence of events that occur when a Linux system starts up. With **systemd**, it involves the following steps:

#### 1. **BIOS/UEFI Initialization**
   - The BIOS/UEFI initializes hardware and performs POST (Power-On Self-Test).
   - Hands control to the bootloader.

#### 2. **Bootloader Execution**
   - The bootloader (e.g., GRUB) loads the kernel and initramfs into memory.
   - Configuration stored in `/boot/grub/grub.cfg`.

#### 3. **Kernel Initialization**
   - Loads device drivers and mounts the root filesystem.
   - Starts `systemd` as the first process (PID 1).

#### 4. **systemd Targets**
   - Targets define the system's state, replacing traditional runlevels.
     - `multi-user.target`: Command-line multi-user mode.
     - `graphical.target`: Full GUI environment.

#### 5. **Execution of Unit Files**
   - Starts unit files such as:
     - `*.service`: Services (e.g., `apache2.service`).
     - `*.mount`: Mount points (e.g., `/var`).

#### Example Output of `systemctl list-units`:
```bash
aftab@linux:~$ systemctl list-units
```
```plaintext
UNIT                         LOAD   ACTIVE SUB     DESCRIPTION
proc-sys-fs-binfmt_misc.automount loaded active waiting Arbitrary Executable File Formats File System
basic.target                 loaded active active  Basic System
multi-user.target            loaded active active  Multi-User System
```

---

### **Q3. What Do You Understand by a Linux Distribution? Enlist 5 Commonly Used Linux Distributions and Their Base Purpose.**

#### **What is a Linux Distribution?**
A **Linux distribution (distro)** is an operating system based on the Linux kernel. It includes:
- **Core Utilities**: GNU tools and libraries.
- **Desktop Environments**: GNOME, KDE, XFCE.
- **Package Managers**: Tools for software management (e.g., `apt`, `yum`).

#### **Popular Linux Distributions**
| **Distribution** | **Purpose**                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| **Ubuntu**        | User-friendly for desktops and servers, ideal for beginners.               |
| **CentOS/AlmaLinux** | Enterprise-grade stability for production servers.                      |
| **Arch Linux**    | Highly customizable, for advanced users who prefer minimalism.             |
| **Kali Linux**    | Used for penetration testing and cybersecurity.                            |
| **Debian**        | Known for stability, used in servers and desktops.                         |

**Example Output of `lsb_release -a`**:
```bash
aftab@linux:~$ lsb_release -a
```
```plaintext
Distributor ID: Ubuntu
Description:    Ubuntu 22.04.3 LTS
Release:        22.04
Codename:       jammy
```

---

### **Q4. What Kind of Partition Would You Create for Hosting a Website?**

#### **Partitioning Scheme**
| **Partition** | **Size**   | **Purpose**                                                                 |
|---------------|------------|-----------------------------------------------------------------------------|
| `/boot`       | 500 MB     | Contains bootloader and kernel files.                                       |
| `/` (root)    | 20 GB      | Primary filesystem containing system binaries and libraries.                |
| `/var`        | 10 GB      | Dedicated for logs, cache, and spool files.                                 |
| `/srv`        | 50–100 GB  | Stores web application content (e.g., `/var/www/html`).                     |
| `/tmp`        | 5–10 GB    | Temporary files used by applications or during updates.                     |
| Swap          | 2× RAM     | Virtual memory, providing stability during heavy loads.                     |

#### **Details**
1. **`/boot`**: Isolated to protect boot-critical files.
2. **`/srv`**: Dedicated to hosting website files for scalability.
3. **Swap**: Prevents memory issues under heavy load.

Example Partition Table for a 500 GB Disk:
| **Partition** | **Size**   | **Filesystem Type** | **Purpose**              |
|---------------|------------|---------------------|--------------------------|
| `/boot`       | 500 MB     | ext4                | Kernel files.            |
| `/srv`        | 300 GB     | ext4                | Website files.           |
| `/var`        | 20 GB      | ext4                | Logs and cache files.    |

---

### **Q5. Enlist 10 Useful Commands in Linux for System and Hardware Information**

#### **Command 1: uname**
```bash
aftab@linux:~$ uname -a
```
**Output**:
```plaintext
Linux aftab-server 5.15.0-46-generic #49-Ubuntu SMP Thu Sep 7 23:48:32 UTC 2023 x86_64 GNU/Linux
```

#### **Command 2: lsblk**
```bash
aftab@linux:~$ lsblk -f
```
**Output**:
```plaintext
NAME   FSTYPE   LABEL    SIZE MOUNTPOINT
sda                      500G
├─sda1 ext4              500M /boot
├─sda2 ext4               20G /
├─sda3 ext4               20G /var
└─sda4 ext4              300G /srv
```

#### **Command 3: df**
```bash
aftab@linux:~$ df -hT
```
**Output**:
```plaintext
Filesystem     Type  Size  Used Avail Use% Mounted on
/dev/sda2      ext4   20G   4G   16G  20% /
/dev/sda3      ext4   20G   5G   15G  25% /var
/dev/sda4      ext4  300G  50G  250G  17% /srv
```

#### **Command 4: free**
```bash
aftab@linux:~$ free -m
```
**Output**:
```plaintext
              total        used        free      shared  buff/cache   available
Mem:          7989        1234        5467         213        1287        6312
Swap:         4096           0        4096
```
