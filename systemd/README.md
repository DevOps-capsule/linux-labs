
### **Advanced Hands-on Lab: Managing Services with systemd and init.d**

#### **Objective:**
Gain advanced experience in managing Linux services using `systemd` and `init.d`, including starting, stopping, enabling, disabling, and inspecting services.

---

### **Lab Requirements:**
- A Linux system with `systemd` (e.g., Ubuntu 20.04+/CentOS 7+/Debian 10+)
- Root or sudo privileges

---

### **Part 1: Working with `systemd` Services**

#### **1. List Available Services**
```bash
systemctl list-units --type=service
```

#### **2. Check the Status of a Service**
Check the status of the `cron` (or `crond`) service:
```bash
systemctl status cron   # Debian/Ubuntu
systemctl status crond  # RHEL/CentOS
```

#### **3. Start and Stop a Service**
```bash
sudo systemctl stop cron
sudo systemctl start cron
```

#### **4. Enable and Disable a Service at Boot**
```bash
systemctl status cron	# Observe that it is already enabled
sudo systemctl disable cron	# Disabling it on boot
sudo systemctl enable cron	# revert it to the original condition
systemctl status cron	# Verify
```

#### **5. View Logs for a Service**
```bash
journalctl -u cron
```

---

### **Part 2: Create a Custom `systemd` Service**

#### **1. Create a Logging Script**
```bash
echo -e '#!/bin/bash\ndate >> /var/log/hello.log' | sudo tee /usr/local/bin/hello.sh
sudo chmod +x /usr/local/bin/hello.sh
```

#### **2. Create a Unit File**
```bash
sudo tee /etc/systemd/system/hello.service > /dev/null <<EOF
[Unit]
Description=Hello Logger Service

[Service]
ExecStart=/usr/local/bin/hello.sh

[Install]
WantedBy=multi-user.target
EOF
```

#### **3. Enable and Start the Custom Service**
```bash
sudo systemctl daemon-reload	# Reload Systemd daemon to re-read the list of services and thus see  our new service called hello
systemctl status hello	# Verify that is now a service
sudo systemctl start hello	# Start/run the service
sudo systemctl enable hello	#Enable on boot
```

#### **4. Verify Functionality**
```bash
cat /var/log/hello.log	# Viewing the logging file directly
journalctl -u hello		# Using journalctl to view the logs
```

---

### **Part 3: Working with `init.d` Services**

#### **1. List init.d Scripts**
```bash
ls /etc/init.d/
```
#### **2. Check Status (if supported)**
```bash
sudo /etc/init.d/cron status
```
#### **3. Start and Stop a Service Using init.d**
```bash
sudo /etc/init.d/cron stop
sudo /etc/init.d/cron start
```
---

### **Part 4: CLean up**
```bash
sudo rm /etc/systemd/system/hello.service	# Removing the unit file
sudo rm /var/log/hello.log	# Removing the log file
sudo rm /usr/local/bin/hello.sh		# Removing the script itself
sudo systemctl daemon-reload	# Reloading the daemon to reflect the changes
systemctl status hello		# Verify that the service has been removed
```

---

### **Bonus (Optional)**
- Create a timer unit in systemd that runs the `hello.sh` script every 5 minutes.
- Explore the use of `chkconfig` on older systems.
