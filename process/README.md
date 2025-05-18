
### **Hands-On Lab: Process Management and systemd in Linux**

#### **Objective**  
This lab introduces process management in Linux, including monitoring, controlling, and managing processes with `ps`, `top` and `kill`.

#### **Prerequisites**  
- A Linux system (Ubuntu, CentOS, or any other distribution)  
- Terminal access  

---

## **Lab Steps**

### **Step 1: Viewing Running Processes**
1. **List all running processes**  
   ```bash
   ps aux
   ```
   - Displays active processes with details like PID, CPU usage, memory usage, and owner.

2. **List processes hierarchically**  
   ```bash
   pstree -p
   ```
   - Shows the parent-child relationship between processes.

3. **Monitor processes in real-time**  
   ```bash
   top
   ```
   or
   ```bash
   htop
   ```
   - Provides real-time process monitoring (use `q` to exit).

---

### **Step 2: Managing Processes**
1. **Start a process in the background**  
   ```bash
   sleep 100 &
   ```
   - Runs `sleep 100` in the background.

2. **View background jobs**  
   ```bash
   jobs
   ```
   - Lists active background jobs.

3. **Bring a job to the foreground**  
   ```bash
   fg %1
   ```
   - Brings job number 1 to the foreground.

4. **Suspend and resume a process**  
   ```bash
   Ctrl+Z  # Suspend foreground process (sleep 100 that is running from the previous step)
   bg      # Resume process in the background (will resume the sleep 100 in the background)
   jobs    # Should tell you that the process "sleep 100 is Running"
   ```

---

### **Step 3: Killing Processes**
1. **Find a process ID (PID) by name**  
   ```bash
   pgrep sleep    # If it tells you that the sleep process is Done re-run it again and continue this step using: sleep 100
   ```

2. **Terminate a process**  
   ```bash
   kill <PID>  # The PID that you got from the pgrep command
   ```
   - Sends a SIGTERM signal to gracefully stop the process.

3. **To kill all processes of a specific name. Just for reference, don't execute!!!**  
   ```bash
   pkill -f sleep
   ```
---

### **Lab Summary**
In this lab, you learned how to:  
✅ Monitor and manage processes with `ps`, `top`, and `htop`.  
✅ Start, stop, and kill processes using `kill` and `pkill`.  

---

### **Bonus Challenge**
Try the following extra tasks:  
🔹 Modify the priority of a process using `nice` and `renice`.  
