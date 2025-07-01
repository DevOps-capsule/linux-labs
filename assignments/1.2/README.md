
### **Linux Systems Assignment: Advanced User, File, and Shell Operations**

#### **Objective**
This assignment will guide students through practical exercises involving Linux filesystem links, redirection, shell scripting variables, user/group management, and administrative access control.

#### **Instructions**
Perform the following tasks on a Linux machine. Record the command you use, its output, and any observations. Submit a markdown or PDF report with your answers.

---

### **Section 1: Inodes and File Linking**
1. Create a file `original.txt` and write some text into it.
2. Create a hard link `hard.txt` and a symbolic link `soft.txt` to the original file
3. Use `ls -li` to inspect inode numbers of all files.
4. Delete `original.txt` and observe the behavior of `hard.txt` and `soft.txt`.
5. Explain the behavior and how inodes are involved.

---

### **Section 2: Input/Output Redirection and Piping**
1. Use `>` and `>>` to write to and append the output of find / -name passwd to `output.txt`.
2. Redirect stderr to a file `error.txt`
3. Combine stdout and stderr in a single file `out-error.txt`
4. Create a pipeline that lists all running processes and filters for `bash`.
5. Use `tee` to write and display output simultaneously.

---

### **Section 3: Creating and Editing Files with Vim**
1. Use `vim vimtest.txt` to open a new file.
2. Insert any paragraph using insert mode.
3. Practice the following:
   - Save and exit
   - Delete a line (using vim shortcuts)
   - Copy and paste any lines (using vim shortcuts)
   - Search (`/word`)

---

### **Section 4: Shell Variables**
1. Create user-defined variables in a terminal that holds your name
2. Print the value of the variable
3. Export a variable and use it in a child shell
4. List all environment variables and verify that the previously exported variable is also an environment variable

---

### **Section 5: User and Group Management**
1. Create a new user `charlie`, make sure to create its home directory
2. Set a password for the user
3. Set the default shell to bash for charlie
4. Create a group `ops` and assign `charlie` to it

---

### **Section 6: Logging In and Gaining Superuser Access**
1. Switch user to `root`
2. Grant `ops` group sudo access:
   ```bash
   sudo visudo
   # Add the line:
   %ops ALL=(ALL) NOPASSWD: ALL
   ```
   Explain this command and what does NOPASSWD do?

3. Verify sudo access by switching to `charlie` again and running:
   ```bash
   sudo whoami
   ```
4. Switch back to your normal user  

---

### **Section 7 (Bonus): Password Policies**
1. View and edit the password policy file:
   ```bash
   sudo nano /etc/login.defs
   ```
   - Identify parameters like `PASS_MAX_DAYS`, `PASS_MIN_DAYS`, `PASS_WARN_AGE`. 
 
2. Explain how each parameter affects user password security and aging in the upcoming steps 3 and 4:  
3. Set password expiration and aging for `charlie`:
   ```bash
   sudo chage -l charlie
   sudo chage -M 30 -m 7 -W 5 charlie
   ```
4. Force `charlie` to change password on next login:
   ```bash
   sudo chage -d 0 charlie
   ```

---

### **Submission**
- Submit the following:
  - All commands used
  - Output screenshots
  - Short explanation for each section
  - A brief summary of what was learned and any challenges faced
