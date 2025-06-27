
### **Hands-On Assignment: Introduction to Linux Essentials**

#### **Objective**
This assignment guides learners through foundational topics in Linux including distributions, architecture, Bash basics, command-line access, and the Linux file system.

#### **Prerequisites**
- A Linux system (any distribution: Ubuntu, CentOS, Debian, etc.)
- Terminal or SSH access

---

### **Part 1: Exploring Linux Distributions**
1. Identify your current Linux distribution:
   ```bash
   cat /etc/os-release
   lsb_release -a  # if available
   uname -a
   ```
2. Research another Linux distribution (Red Hat based if you you're using Debian based distribution and vice verse) and note the differences in package manager, default file system, and target use case.

---

### **Part 2: Investigating Linux Architecture**
1. Display system architecture:
   ```bash
   uname -m  # Check the current hardware architecture of your machine
   ```

2. Use the same command help function to identify your OS kernel-release!
---

### **Part 4: Bash Shell Basics and Shortcuts**
1. Test the Bash shell version:
   ```bash
   echo $BASH_VERSION	# Search inline about this command to understand what is $BASH_VERSION
   ```

2. List the installed shells!

3. Get the current active shell!

4. Use command history and `alias`:
   ```bash
   history
   alias ll='ls -l'		# Search about this!!
   ```

---

### **Part 5: Bash Simple Commands Practice**
1. Tell me the outcomes of each command of the following:
   ```bash
   mkdir ~/linux_practice
   cd ~/linux_practice
   touch hello.txt
   echo "Hello World" > hello.txt
   ```
2. View and edit files:
   ```bash
   cat hello.txt
   nano hello.txt	# Search about nano, what is it?
   ```
3. Search using `grep`:
   ```bash
   grep Hello hello.txt
   ```
4. Count lines, words, and characters:
   ```bash
   wc hello.txt
   ```

---

### **Part 6: Exploring the Linux File System Structure**
1. List root-level directories and describe their purposes:
   ```bash
   tree -L 1 /  # This will print the first level of the root directory
   ```
   Focus on `/etc`, `/home`, `/bin`, `/usr`, `/var`, `/tmp`, `/lib`, and `/opt`
2. Explore a few directory contents:
   ```bash
   ls /etc
   ls /usr/bin | head  # Explain this command!!
   ```
3. Write down the command that is used for inspecting the current disk usage in a human readable format!

---

### **Assignment Submission Requirements**
- Submit a markdown or PDF document including:
  - Screenshots or output of the commands
  - Brief explanations for each step
  - Notes or reflections on what you learned

---

### **Bonus Challenge**
🔹 Try logging in remotely using SSH to another Linux machine (or localhost)  
🔹 Create a bash script that runs a sequence of basic commands (e.g., `mkdir`, `touch`, `echo`, `cat`)  
🔹 Use `man` pages to explore command options (e.g., `man ls`, `man grep`)
