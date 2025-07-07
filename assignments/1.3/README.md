
# Assignment: Linux Process Management, Services, and Secure SSH

## Objective
This assignment evaluates your understanding of:
- Monitoring and managing Linux processes
- Controlling foreground and background jobs
- Managing services using systemd
- Configuring and securing SSH using key-based authentication

Answer the following questions based on your experience or research. You are encouraged to test these tasks in a Linux environment and reflect on your results.

---

## Section 1: Process Management Tools

1. What tools can be used to list and monitor running processes in Linux?
2. How can you determine which processes consume the most system resources?
3. What is the difference between a zombie process and an orphan process?
4. Explain why a zombie process can't be killed by itself? and the way that is used to kill a zombie process?
5. How do you safely terminate a process, and what are the available signal types?
6. How can you change the priority of a process while it is running?

---

## Section 2: Foreground and Background Job Control

1. What is the difference between foreground and background jobs in a shell session?
2. How do you send a running job to the background?
3. How do you bring a background job back to the foreground?
4. What command shows a list of current background jobs?
5. What happens to background jobs when the terminal session is closed?

---

## Section 3: Managing Services with systemd

1. How do you check the status of a service using systemd?
2. Describe how to start, stop, and restart a service.
3. What is the difference between enabling and starting a service?
4. How can you view a list of all services and their statuses?
5. Why is systemd preferred over traditional init systems for managing services?

---

## Section 4: SSH Key-Based Authentication and Security

1. What is the purpose of using SSH for remote access?
2. Describe the process of generating SSH keys and configuring key-based login.
3. How can you confirm that key-based SSH authentication is working?
4. What configuration changes are needed to disable password-based SSH logins?
5. What are the security benefits of using SSH keys instead of passwords?
6. What precautions should you take before disabling password authentication?

---
## Section 5: Advanced file permissions

1. Explain the special file permissions that uses `suid`, `sgid` and `sticky`
2. Explain why the `passwd` command work while you don't have permissions on `/etc/shadow` (can be explained if you understand the special permissions in the previous question).
3. Explain ACLs (Access Control List in linux), and the benefits it provide compared to the standard Linux permissions
---

## Submission Guidelines

- Submit your answers in a Markdown or PDF format.
- Include any screenshots or observations from your own testing.
- Provide a short summary of what you learned and any challenges you faced.
