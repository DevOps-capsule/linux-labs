
### **Linux Systems Assignment: Storage and Networking Essentials**

#### **Objective**
To assess practical skills in storage and networking fundamentals in Linux.

---

### **Part 1: Partition Tables (Practice)**

#### **Instructions:**
##### **Caution: This step is not mandatory but if you want to do it, take a backup of your virtual machine before starting!!**
1. Use a virtual or physical disk (e.g., `/dev/sdb`) to:
   - Create a partition using `fdisk` or `parted`.
   - Display the partition layout using `lsblk` and `fdisk -l`.

---

### **Part 2: File Systems (Practice)**

1. Use a loopback file or secondary disk (e.g., `/dev/sdb`) to:
   - Format the partition as `ext4` and `xfs` (use different loopback images).
   - Mount the partitions to `/mnt/ext4_test` and `/mnt/xfs_test`.
   - Create a sample file on each and verify the content.

2. Unmount the filesystems and clean up.

---

### **Part 3: Mounting and Unmounting Volumes (Practice)**

#### **Instructions:**
1. Create a 100MB file loop device using `dd` and format it as `ext4`:
   ```bash
   dd if=/dev/zero of=disk.img bs=1M count=100
   mkfs.ext4 disk.img
   ```

2. Mount it at `/mnt/testvolume`:
   ```bash
   mkdir /mnt/testvolume
   sudo mount -o loop disk.img /mnt/testvolume
   ```

3. Add an entry to `/etc/fstab` to auto-mount it at boot (mark the line with a comment for easy removal).
4. Unmount the volume and remount using the `mount -a` command:
   ```bash
   sudo umount /mnt/testvolume
   sudo mount -a
   ```

---

### **Part 4: Networking Concepts (Practice)**

1. View your IP configuration using:
   ```bash
   ip a
   ```
   or
   ```bash
   nmcli device show
   ```

2. Use the following tools and capture screenshots/output for each:
   - `ping` to test connectivity to `8.8.8.8`
   - `traceroute` to `google.com`
   - `netstat` or `ss` to view listening ports
   - `nmap` to scan a local host (use `localhost` or `127.0.0.1`)

---

### **Submission Requirements**
- A single PDF or markdown file that includes:
  - Terminal output/screenshots of each task.
  - A brief reflection on what was learned.

---

### **Bonus (Optional)**
- Use `tcpdump` to capture a short packet trace (on your own test system or VM).