
### **Hands-On Lab: Navigating the Linux File System and Basic File Operations**  

#### **Objective**  
This lab will introduce beginners to fundamental Linux commands for navigating the file system, working with files, searching content using `grep`, and editing files using `nano`.  

#### **Prerequisites**  
- A Linux system (Ubuntu, CentOS, or any other distribution)  
- Terminal access  

---

## **Lab Steps**

### **Step 1: Navigating the File System**
1. **Open a terminal.**  
2. **Check your current directory (Present Working Directory - PWD)**  
   ```bash
   pwd
   ```
   - This command displays the full path of the directory you are currently in.

3. **List the contents of a directory**  
   ```bash
   ls
   ```
   - Shows the files and directories in the current directory.

4. **List contents in a detailed format**  
   ```bash
   ls -l
   ```
   - Displays detailed information, including file size, permissions, and modification time.

5. **Move into the `/tmp` directory**  
   ```bash
   cd /tmp
   ```

6. **Move back to your home directory**  
   ```bash
   cd ~
   ```
   or  
   ```bash
   cd
   ```

7. **Create a new directory called `lab` and navigate into it**  
   ```bash
   mkdir lab
   cd lab
   ```

---

### **Step 2: Creating and Displaying Files**
1. **Create a new file called `example.txt`**  
   ```bash
   touch example.txt
   ```

2. **Write some text into the file using `echo`**  
   ```bash
   echo "Hello, this is a Linux file system lab." > example.txt
   ```

3. **Display the contents of the file using `cat`**  
   ```bash
   cat example.txt
   ```
   - This prints the file content to the terminal.

4. **Use `less` to view the file (useful for large files)**  
   ```bash
   less example.txt
   ```
   - Press `q` to exit `less`.

5. **Use `head` to display the first 5 lines of the file**  
   ```bash
   head -5 example.txt
   ```

6. **Use `tail` to display the last 5 lines of the file**  
   ```bash
   tail -5 example.txt
   ```

---

### **Step 3: Searching Inside Files Using `grep`**
1. **Add some content to `example.txt`**  
   ```bash
   echo "Linux is powerful" >> example.txt
   echo "I love using Linux" >> example.txt
   ```

2. **Search for the word "Linux" in `example.txt`**  
   ```bash
   grep "Linux" example.txt
   ```

3. **Perform a case-insensitive search**  
   ```bash
   grep -i "linux" example.txt
   ```

4. **Show line numbers where the word "Linux" appears**  
   ```bash
   grep -n "Linux" example.txt
   ```

---

### **Step 4: Editing Files Using Nano**
1. **Open the file using `nano`**  
   ```bash
   nano example.txt
   ```

2. **Inside `nano`:**
   - Use the arrow keys to navigate the text.
   - Add a new line: `"Nano is a simple text editor."`
   - Press `CTRL + X` to exit.
   - Press `Y` to save changes.
   - Press `Enter` to confirm the filename.

3. **Verify the changes by displaying the file content**  
   ```bash
   cat example.txt
   ```

---

### **Step 5: Cleaning Up**
1. **Remove the file**  
   ```bash
   rm example.txt
   ```

2. **Remove the directory and its contents**  
   ```bash
   cd ..
   rm -r lab
   ```

---

### **Lab Summary**
In this lab, you learned how to:  
✅ Navigate the Linux file system using `cd`, `ls`, and `pwd`  
✅ Create and display file contents using `touch`, `cat`, `less`, `head`, and `tail`  
✅ Search for text in files using `grep`  
✅ Edit files using the `nano` text editor  

---

### **Bonus Challenge**
Try the following extra tasks:  
🔹 Create another directory and copy files into it using `cp`.  
🔹 Use `mv` to rename a file.  
🔹 Use `grep` with the `-v` option to exclude a specific word from search results.  

Would you like additional explanations or modifications to this lab? 😊