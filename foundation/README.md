
### **Hands-On Lab: Introduction to Linux and System Overview**

#### **Objective**  
To provide beginners with foundational knowledge of Linux, including its distributions, system architecture, and filesystem structure. This lab includes hands-on tasks and commands to solidify understanding.

---

## **Lab Outline**

### **1. Overview of Linux**
Linux is an open-source, Unix-like operating system kernel that forms the foundation for many operating systems (distributions). It is widely used in servers, desktops, embedded systems, and mobile devices.

#### **Hands-On Task**:
- Check the Linux kernel version:
  ```bash
  uname -r
  ```
- Check system information:
  ```bash
  uname -a
  lsb_release -a  # On Ubuntu/Debian
  cat /etc/os-release  # On most distributions
  ```

---

### **2. Linux Distributions**
Popular Linux distributions include:
- **Debian/Ubuntu-based**: Ubuntu, Linux Mint
- **Red Hat-based**: RHEL, CentOS, Fedora, AlmaLinux
- **Others**: Arch Linux, openSUSE, Gentoo

Each distribution packages the Linux kernel with specific utilities and package managers.

#### **Hands-On Task**:
- Determine your current distribution:
  ```bash
  cat /etc/*release*
  ```
- Explore available distributions at [DistroWatch](https://distrowatch.com) if you want, but not during the lab time

---

### **3. Comparison and Choosing the Right One**
| Feature            | Ubuntu/Debian | RHEL/CentOS/Fedora | Arch Linux   |
|--------------------|----------------|---------------------|--------------|
| Target Audience    | Beginners      | Enterprises         | Advanced Users |
| Package Manager    | apt            | yum/dnf             | pacman       |
| Stability          | High           | Very High (RHEL)    | Rolling Release |
| Documentation      | Extensive      | Enterprise-grade     | Community-driven |

#### **Hands-On Task**:
- Use package manager command:
  ```bash
  sudo apt update        # Debian/Ubuntu
  sudo dnf update        # RHEL/CentOS/Fedora
  sudo yum update        # RHEL/CentOS/Fedora
  ```

---

### **4. Layers of Abstraction in a Linux System**
1. **Hardware** – Physical components
2. **Kernel** – Manages hardware and system calls
3. **Shell** – Command interpreter for users
4. **Utilities/Applications** – User-space tools (bash, nano, gcc, etc.)

#### **Hands-On Task**:
- View current shell:
  ```bash
  echo $SHELL
  ````
- List installed shells:
  ```bash
  cat /etc/shells
  ```
- Check the kernel ring buffer (hardware-level messages just for fun):
  ```bash
  dmesg | head -20
  ```

---

### **5. Linux Filesystem Structure**
| Directory | Purpose |
|----------|---------|
| `/`      | Root directory |
| `/bin`   | Essential binaries |
| `/sbin`  | System binaries |
| `/etc`   | Configuration files |
| `/home`  | User directories |
| `/var`   | Variable files (logs, spools) |
| `/tmp`   | Temporary files |
| `/usr`   | User-installed software |
| `/lib`   | Shared libraries |
| `/boot`  | Bootloader files |
| `/dev`   | Device files |
| `/proc`  | Kernel and process info |

#### **Hands-On Task**:
- Navigate through directories and inspect contents:
  ```bash
  cd /
  ls
  ls /etc
  ls /var
  ls /usr
  ```
- Explore processes and hardware via `/proc`:
  ```bash
  ps -ef | head # gets the first few lines of the ps command which displays the processes
  cat /proc/cpuinfo
  cat /proc/meminfo
  ```
- Check disk space usage:
  ```bash
  df -h	#-h displays human readable format, to understand run just df and observe the difference
  df
  ```

---

## **Lab Summary**
✅ Gained understanding of what Linux is and its key components  
✅ Explored different distributions and their use cases  
✅ Investigated Linux system layers and their interactions  
✅ Navigated and examined the Linux filesystem  

---