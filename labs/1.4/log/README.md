
# 🧪 Hands-On Lab: Working with rsyslog Rules and journald

## 🎯 Objective
In this lab, you will:
- Create and test custom rsyslog rules
- Explore how journald logs system events
- Understand how rsyslog and journald can work together or independently

---

## 🔧 Prerequisites
- A Linux system with `rsyslog` and `systemd-journald` installed (most modern distros)
- Root/sudo access to the machine
- A test user account (optional for testing user logs)

---

## 📌 Part 1: Understanding rsyslog Rules and Testing

### Step 1: Verify rsyslog Status
Check that rsyslog is running:
```bash
systemctl status rsyslog
```

### Step 2: Create a Custom rsyslog Rule
Edit or create a new configuration file in `/etc/rsyslog.d/`:
```bash
sudo nano /etc/rsyslog.d/20-custom.conf
```
Add the following line to log `local6` facility messages to a custom log file:
```
local6.*   /var/log/custom_app.log
```

### Step 3: Restart rsyslog
```bash
sudo systemctl restart rsyslog
```

### Step 4: Generate a Test Message
Use the `logger` command to generate a test message:
```bash
logger -p local6.info "This is a test message to custom_app.log"
```

### Step 5: Verify Log Output
Check if the message was written to the log:
```bash
cat /var/log/custom_app.log
```

You should see the test message logged.

---

## 📌 Part 2: Exploring Journald

### Step 1: Inspect Journald Configuration
View the configuration file:
```bash
cat /etc/systemd/journald.conf
```


### Step 2: View Logs Using journalctl
- Show all logs:
  ```bash
  journalctl
  ```
- Show logs since boot:
  ```bash
  journalctl -b
  ```
- Filter logs by a service:
  ```bash
  journalctl -u sshd
  ```
- Show real-time log output:
  ```bash
  journalctl -f
  ```

---

## 🧹 Cleanup (Optional)
- Remove the custom config file:
  ```bash
  sudo rm /etc/rsyslog.d/20-custom.conf
  sudo systemctl restart rsyslog
  ```
- Delete the test log:
  ```bash
  sudo rm /var/log/custom_app.log
  ```

---

## ❓ Review Questions
1. What is the purpose of the `local6.*` rule in rsyslog?
2. How does `logger` help in testing rsyslog configurations?