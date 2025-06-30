### **Hands-On Lab: Managing Files from the Command Line Interface (CLI)**

#### **Objective**
Learn to navigate and manipulate files and directories from the Linux command line using both absolute and relative paths.

#### **Prerequisites**
- A working Linux environment
- Terminal or SSH access

---

### **Part 1: Identifying Linux File Types (Command Practice Only)**

1. View file information using `ls`:
   ```bash
   ls -l
   ```
2. Determine file type using the `file` command:
   ```bash
   file /bin/ls
   file ~/test_file.txt
   ```
3. Use `stat` to get detailed file metadata:
   ```bash
   stat /etc/passwd
   ```

---

### **Part 2: Working with Absolute and Relative Paths**

1. Navigate using an absolute path:
   ```bash
   cd /usr/bin
   pwd
   ```

2. Navigate using a relative path:
   ```bash
   cd ../../etc
   pwd
   ```

3. Move back to the home directory:
   ```bash
   cd ~
   cd
   ```

4. Use `.` and `..` for relative navigation:
   ```bash
   cd /var/log
   cd ..
   cd ./log
   ```

---

### **Part 3: Managing Files and Directories**

1. Create directories and files:
   ```bash
   mkdir -p ~/cli_lab/demo
   touch ~/cli_lab/demo/file1.txt
   echo "Hello CLI Lab" > ~/cli_lab/demo/file1.txt
   ```

2. Copy files and directories:
   ```bash
   cp ~/cli_lab/demo/file1.txt ~/cli_lab/demo/file2.txt
   cp -r ~/cli_lab/demo ~/cli_lab/backup_demo
   ```

3. Move and rename files:
   ```bash
   mv ~/cli_lab/demo/file2.txt ~/cli_lab/demo/renamed_file.txt
   ```

4. Remove files and directories:
   ```bash
   rm ~/cli_lab/demo/renamed_file.txt
   rm -r ~/cli_lab/backup_demo
   ```

5. Use wildcard characters:
   ```bash
   ls ~/cli_lab/demo/*.txt
   ```

6. View directory tree and disk usage:
   ```bash
   tree ~/cli_lab
   du -sh ~/cli_lab
   ```

---
