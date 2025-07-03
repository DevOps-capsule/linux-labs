
### **Hands-On Lab: Secure SSH Access and Key-Based Authentication**

#### **Objective**
Practice secure remote access to a Linux system using SSH, configure key-based authentication for password-less login, and disable password authentication for enhanced security.

#### **Prerequisites**
- Access to two Linux machines (local and remote), or a virtual machine that can be accessed remotely.
- SSH service (`sshd`) must be installed and running on the remote system.

---

### **Part 1: Log Into a Remote System Using SSH**
1. From your local machine, connect to the remote machine using:
   ```bash
   ssh username@remote_ip
   ```
2. If prompted to continue connecting, type `yes` and enter the password.
3. Run a few basic commands on the remote machine:
   ```bash
   hostname
   whoami
   uptime
   ```
4. Exit the remote machine
---

### **Part 2: Configure Key-Based Authentication**

1. **Generate SSH Key Pair on your Local Machine:**
   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com" -f ~/Desktop/my_ssh_key
   ```
   Press `Enter` to accept and (optionally) enter a passphrase.

2. **Copy the Public Key to the Remote Machine:**
   ```bash
   ssh-copy-id -i ~/Desktop/my_ssh_key.pub username@remote_ip
   ```
   Or manually:
   ```bash
   cat ~/Desktop/my_ssh_key.pub | ssh username@remote_ip 'mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys && chmod 600 ~/.ssh/authorized_keys'
   ```

3. **Test Password-less SSH Login:**
   ```bash
   ssh -i ~/Desktop/my_ssh_key username@remote_ip
   ```
   You should be logged in without being prompted for a password.

---

### **Part 3: Disable Password Authentication (Remote Host)**

1. **Edit SSH Configuration File:**
   ```bash
   sudo nano /etc/ssh/sshd_config
   ```
   Find and change or add these lines:
   ```
   PasswordAuthentication no
   ```

2. **Reload SSH Service:**
   ```bash
   sudo systemctl reload sshd
   ```

3. **Test Again:**
   - Try logging in using key-based SSH `ssh -i ~/Desktop/my_ssh_key username@remote_ip` (should work)
   - Try logging in again without the key `ssh username@remote_ip` (should fail after asking for a password)

> ⚠️ *Ensure you are still logged into the remote machine through another terminal before disabling password login, to avoid being locked out.*

---
