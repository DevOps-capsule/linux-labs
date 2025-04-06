### **Hands-On Lab: Package Management in Linux**

#### **Objective**  
This lab provides hands-on experience with package management in Linux using `apt` (Debian-based distributions) and `yum` (RHEL-based distributions). You will learn to install, update, remove, and manage software repositories.

#### **Prerequisites**  
- A Linux system (Ubuntu/Debian for `apt`, CentOS/RHEL for `yum`)
- Terminal access with `sudo` privileges

---

## **Lab Steps**

### **Step 1: Updating Package Lists**
1. **Update package lists (Debian-based systems)**  
   ```bash
   sudo apt update
   ```
2. **Update package lists (RHEL-based systems)**  
   ```bash
   sudo yum check-update
   ```

---

### **Step 2: Installing Packages**
1. **Install a package (Debian-based)**  
   ```bash
   sudo apt install htop
   ```
2. **Install a package (RHEL-based)**  
   ```bash
   sudo yum install htop
   ```

---

### **Step 3: Searching for Packages**
1. **Search for a package (Debian-based)**  
   ```bash
   apt search htop
   ```
2. **Search for a package (RHEL-based)**  
   ```bash
   yum search htop
   ```

---

### **Step 4: Viewing Package Information**
1. **Get package details (Debian-based)**  
   ```bash
   apt show vim
   ```
2. **Get package details (RHEL-based)**  
   ```bash
   yum info vim
   ```

---

### **Step 5: Removing Packages**
1. **Uninstall a package (Debian-based)**  
   ```bash
   sudo apt remove htop
   ```
2. **Uninstall a package (RHEL-based)**  
   ```bash
   sudo yum remove htop
   ```

---

### **Step 6: Remove all unused dependencies**
1. **Debian-based**  
   ```bash
   sudo apt autoremove
   ```
2. **RHEL-based**  
   ```bash
   sudo yum autoremove
   ```

---

### **Step 7: Managing Repositories**
1. **List enabled repositories (Debian-based)**  
   ```bash
   cat /etc/apt/sources.list
   ```
2. **List enabled repositories (RHEL-based)**  
   ```bash
   yum repolist
   ```

---

### **Lab Summary**
In this lab, you learned how to:  
✅ Update package lists  
✅ Search, install, and remove packages  
✅ View package information  
✅ Clean up package cache   

---

### **Bonus Challenge**
🔹 Try installing and removing multiple packages at once.  
🔹 Explore `dpkg` (Debian) and `rpm` (RHEL) for low-level package management.  
🔹 Configure a custom repository and install packages from it.  
