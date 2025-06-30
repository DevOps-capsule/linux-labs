### **Hands-On Lab: User and Group Management in Linux**

#### **Objective**
Practice managing locally defined users and groups, and explore how to gain superuser privileges in a Linux environment.

#### **Prerequisites**
- A Linux system (physical or virtual machine)
- Terminal access with sudo privileges

---

### **Part 1: Creating Users and Groups**

1. Switch to the root user
   ```bash
   su
   ```
   
2. Create a new group:
   ```bash
   sudo groupadd devteam
   ```

3. Create a new user and assign to the group:
   ```bash
   sudo useradd -m -G devteam alice # creates new user and adds membership to the supplementary group devteam
   sudo passwd alice # setting password for alice
   ```

4. Verify user and group membership:
   ```bash
   id alice
   groups alice
   ```

---

### **Part 2: Modifying Users and Groups**

1. Add the user to an additional group:
   ```bash
   sudo usermod -aG sudo alice
   ```

2. Rename a group:
   ```bash
   sudo groupmod -n devops devteam
   ```

3. Change user’s primary group:
   ```bash
   sudo usermod -g devops alice
   ```

---

### **Part 3: Deleting Users and Groups**

1. Remove a user:
   ```bash
   sudo userdel -r alice
   ```

2. Delete a group:
   ```bash
   sudo groupdel devops
   ```
