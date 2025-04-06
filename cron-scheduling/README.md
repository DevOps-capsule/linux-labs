
### **Hands-On Lab: Cron Jobs for Scheduling Tasks in Linux**

#### **Objective**  
This lab introduces cron jobs in Linux, helping you understand how to schedule tasks, manage cron jobs, and automate system operations.

#### **Prerequisites**  
- A Linux system (Ubuntu, CentOS, or any other distribution)  
- Terminal access  

---

## **Lab Steps**

### **Step 1: Understanding Cron and Crontab**
1. **Check if cron service is running**  
   ```bash
   systemctl status cron  # Ubuntu/Debian
   systemctl status crond  # CentOS/RHEL
   ```
2. **Start the cron service if it is not running**  
   ```bash
   sudo systemctl start cron  # Ubuntu/Debian
   sudo systemctl start crond  # CentOS/RHEL
   ```
3. **Enable cron to start on boot if not already enabled**  
   ```bash
   sudo systemctl enable cron  # Ubuntu/Debian
   sudo systemctl enable crond  # CentOS/RHEL
   ```

---

### **Step 2: Editing the Crontab**
1. **Open the crontab for the current user**  
   ```bash
   crontab -e
   ```
2. **Add the following cron job to run a script every minute:**  
   ```
   * * * * * echo "Cron Job Test: $(date)" >> ~/cron_test.log
   ```
   - This appends "Cron Job Test" to the cron_test.log file in your home directory `~/cron_test.log` every minute.
3. **Save and exit the editor**  
   - For nano, press `CTRL+X`, then `Y`, then `ENTER`.  
4. open new terminal and run `watch -d ~/cron_test.log` and wait to see the contents of the file get updated every minute

---

### **Step 3: Viewing and Managing Cron Jobs**
1. **List existing cron jobs**  
   ```bash
   crontab -l
   ```
2. **Remove all cron jobs**  
   ```bash
   crontab -r
   ```
3. **View system-wide cron jobs**  
   ```bash
   cat /etc/crontab
   ```

---

### **Step 4: Understanding Cron Syntax**
The cron syntax follows this pattern:
```
* * * * * command_to_execute
| | | | |
| | | | +---- Day of the week (0 - 6) [Sunday = 0]
| | | +------ Month (1 - 12)
| | +-------- Day of the month (1 - 31)
| +---------- Hour (0 - 23)
+------------ Minute (0 - 59)
```
Examples:
- `0 6 * * * /path/to/script.sh` → Runs daily at 6 AM
- `*/15 * * * * /path/to/script.sh` → Runs every 15 minutes
- `0 0 * * 0 /path/to/script.sh` → Runs every Sunday at midnight

---

### **Step 5: Automating a Script with Cron**
1. **Create a script that logs system uptime**  
   ```bash
   nano ~/uptime_logger.sh
   ```
   - Add the following content:
     ```bash
     #!/bin/bash
     echo "System Uptime: $(uptime)" >> ~/uptime.log
     ```
2. **Make the script executable**  
   ```bash
   chmod +x ~/uptime_logger.sh
   ```
3. **Schedule the script to run every hour**  
   ```bash
   crontab -e
   ```
   - Add the line:
     ```
     0 * * * * ~/uptime_logger.sh
     ```

---

### **Step 6: Clean up**
1. **Remove all cron jobs of your user**  
   ```bash
   crontab -r
   ```
---

### **Lab Summary**
In this lab, you learned how to:
✅ Manage cron service  
✅ Create and edit cron jobs  
✅ Understand cron job syntax  
✅ Automate scripts with cron  

---

### **Bonus Challenge**
🔹 Seach about `cron.allow` and `cron.deny` to manage cron permissions.  
