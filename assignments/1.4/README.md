
# 📘 Assignment: Linux Logging, Networking, Scheduling, and Package Management

## Section 1: rsyslog Rules
1. What are the key components of an rsyslog rule?
2. How do facility and severity levels work in rsyslog?
3. Describe how you would configure rsyslog to write `auth` logs to a separate file.
4. How can you test whether the custom rsyslog rule that you just created is working?

---

## Section 2: Log File Rotation
1. What is the purpose of log file rotation?
2. How does `logrotate` determine when to rotate a log file?
3. Describe a typical `logrotate` configuration for daily rotation and keeping 7 backups.
4. How can you manually trigger a log rotation for testing purposes?

---

## Section 3: systemd-journald
1. What is the difference between journald and rsyslog?
2. Where does journald store log data by default?
3. How can you configure journald to persist logs across reboots?
4. How do you view logs for a specific service using `journalctl`?

---

## Section 4: Network Troubleshooting Tools
1. What kind of information can you gather using `traceroute`?
2. What is the difference between `netstat` and `ss`?
3. How would you use `dig` to check if DNS is working correctly?
4. In what situations would you use `tcpdump`? What precautions should be taken?
5. How does `nmap` help in network discovery and security auditing?

---

## Section 5: Cron Job for Backup
1. How do you schedule a cron job to run daily at midnight?
2. Write a cron job that creates a compressed backup of your user's home directory to `/backup` folder.
3. Where can you view a list of current cron jobs for your user?
4. How do you redirect cron job output to a log file?

---

## Section 6: Package Management
1. What are the key differences between `apt` and `yum` package managers?
2. How do you add a new software repository in Debian-based systems?
3. What command would you use to upgrade all installed packages on an Ubuntu system?
4. Describe the steps to remove a package and its configuration files using `apt`.

---

## Section 7: Bonus
1. Search about IP CIDR notation and how to calculate it. write a short description about it!
2. Consider solving the following CIDR 192.168.1.0/22. and write how many IPs usable? and if there are any specific IPs that is reserved by default and can't be used?
3. Search about `awk`, `sed` commands, include description and a few examples on how you can benefit from them (I want some screenshots about your examples)

---

## Submission Instructions
- Submit your answers in a `.md` or `.pdf` format.
- Include any screenshots if you tested commands in a live environment.
- Use examples from your system wherever possible.
