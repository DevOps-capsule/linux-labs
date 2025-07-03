### **Hands-On Lab: Linux File System Permissions and Default umask Settings**

#### **Objective**
Learn how to manage file and directory permissions, change ownership, and configure default permission settings using `umask`.

#### **Prerequisites**
- A Linux environment with terminal access.
- A user account with sudo privileges.

---

### **Part 1: File and Directory Permissions**

1. **Create Test Files and Directories:**
   ```bash
   mkdir ~/perm_lab
   cd ~/perm_lab
   touch file1.txt
   mkdir dir1
   ```

2. **Check Initial Permissions:**
   ```bash
   ls -l
   ```

3. **Change File and Directory Permissions:**
   ```bash
   chmod 700 file1.txt
   chmod 755 dir1
   ls -l
   ```

4. **Use Symbolic and Numeric Modes:**
   ```bash
   chmod u+r file1.txt
   chmod g-w,o-r file1.txt
   chmod 644 file1.txt
   ```

5. **Explore Effects of Execute Permission on Directories:**
   ```bash
   chmod -x dir1
   cd dir1    # Should fail
   chmod +x dir1
   cd dir1    # Should succeed
   ```

---

### **Part 2: Changing Ownership**

1. **Check Ownership:**
   ```bash
   ls -l file1.txt
   ```

2. **Create Another User and Assign Ownership:**
   ```bash
   sudo useradd userb
   sudo chown userb:userb file1.txt
   ls -l file1.txt
   ```

---

### **Part 3: Understanding and Setting umask**

1. **Check Current umask:**
   ```bash
   umask
   ```

2. **Create New Files and Directories:**
   ```bash
   touch testfile.txt
   mkdir testdir
   ls -l
   ```

3. **Change umask Temporarily:**
   ```bash
   umask 027
   touch file027.txt
   mkdir dir027
   ls -l
   ```

4. **Make umask Persistent (Optional):**
   - Add `umask 027` to the bottom of `~/.bashrc` or `~/.profile`.
   ```bash
   echo 'umask 027' >> ~/.bashrc
   source ~/.bashrc
   ```

5. **Don't forget to revert the changes if you applied the latest step**
   
---
> ✅ Tip: Always test permissions by trying to access files or directories as different users to confirm settings are working as expected.
