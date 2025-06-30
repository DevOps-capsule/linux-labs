### **Hands-On Lab: Input/Output Redirection and Text Editing in Linux**

#### **Objective**
Learn to use input/output redirection, piping, and work with text editors (vim and nano) to manage and manipulate text files efficiently in Linux.

#### **Prerequisites**
- A Linux system with `nano` and `vim` installed
- Access to a terminal (local or SSH)

---

### **Part 1: Input/Output Redirection**

1. Create a sample file:
   ```bash
   echo "line one" > sample.txt
   echo "line two" >> sample.txt
   echo "line three" >> sample.txt
   cat sample.txt
   ```

2. Redirect command output to a new file:
   ```bash
   ls -l /etc > etc_list.txt
   head etc_list.txt
   ```

3. Redirect `stderr` to a file:
   ```bash
   ls /nonexistent 2> error.log
   cat error.log
   ```

4. Redirect both `stdout` and `stderr`:
   ```bash
   ls /etc /nonexistent > all_output.log 2>&1
   cat all_output.log
   ```

5. Use input redirection with a command:
   ```bash
   wc -l < sample.txt   # prints the number of lines in the file
   ```

---

### **Part 2: Piping**

1. Chain commands using pipes:
   ```bash
   ps aux | grep ssh
   ```

2. Use multiple commands in a pipeline:
   ```bash
   cat /etc/passwd | grep bash | sort | uniq
   ```

3. Combine `find`, `xargs`, and `ls`:
   ```bash
   find /etc -name "*.conf" | xargs ls -lh
   ```

---

### **Part 3: Creating and Editing Files with nano and vim**

#### **Using nano:**

1. Open a file with nano:
   ```bash
   nano nano_example.txt
   ```

2. Type some text, save (`Ctrl+O`), and exit (`Ctrl+X`).

3. Re-open the file and add more content. Practice cut (`Ctrl+K`) and paste (`Ctrl+U`) operations.

#### **Using vim:**

1. Open a file with vim:
   ```bash
   vim vim_example.txt
   ```

2. Press `i` to enter insert mode. Type some lines.

3. Press `Esc`, type `:wq` to save and quit.

4. Open the file again and practice:
   - Deleting lines with `dd`
   - Copying lines with `yy` and pasting with `p`
   - Searching with `/word`

---

### **Bonus Tasks**
- Create a custom message log using redirection: `echo "$(date) - Log message" >> log.txt`
- Use `tee` to write and display at the same time: `ls -l | tee output.txt`
