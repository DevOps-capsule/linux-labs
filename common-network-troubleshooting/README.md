
### **Hands-On Lab: Networking Basics and Troubleshooting in Linux**  

#### **Objective**  
This lab introduces basic networking concepts in Linux and provides hands-on experience with commands for checking network configurations, testing connectivity, and troubleshooting issues.  

#### **Prerequisites**  
- A Linux system (Ubuntu, CentOS, or any other distribution)  
- Terminal access  

---

## **Lab Steps**

### **Step 1: Checking Network Configuration**
1. **View network interfaces and IP addresses**  
   ```bash
   ip a
   ```
   or
   ```bash
   ifconfig
   ```
   - Lists active network interfaces and their assigned IP addresses.

2. **View the default gateway**  
   ```bash
   ip route show
   ```
   or
   ```bash
   route -n
   ```
   - Displays the system’s routing table.

3. **View DNS settings**  
   ```bash
   cat /etc/resolv.conf
   ```
   - Shows the configured DNS servers (observe the nameserver variable).

---

### **Step 2: Testing Network Connectivity**
1. **Check connectivity to a remote host using `ping`**  
   ```bash
   ping -c 4 google.com
   ```
   - Sends 4 ICMP packets to Google to test connectivity.

2. **Check if a specific port is open using `nc` (netcat)**  
   ```bash
   nc -zv google.com 80
   ```
   - Checks if port 80 (HTTP) is open on Google’s server.

3. **Test name resolution with `nslookup` or `dig`**  
   ```bash
   nslookup google.com
   ```
   or
   ```bash
   dig google.com
   ```
   - Resolves domain names to IP addresses.

4. **Check the route packets take using `traceroute` or `tracepath`**  
   ```bash
   traceroute google.com
   ```
   - Displays the hops taken by packets to reach their destination.
   - If not installed (Debian): `sudo apt update` and `sudo apt install traceroute`
   - If not installed (RHEL): `sudo yum check-update` and `sudo yum install traceroute`

---

### **Step 3: Troubleshooting Network Issues**
1. **Check if a network interface is active**  
   ```bash
   ip link show
   ```
   - Identifies whether an interface is `UP` or `DOWN`.

2. **Restart a network interface (replace `eth0` with the correct interface)**  
   ```bash
   sudo ip link set eth0 down
   sudo ip link set eth0 up
   ```

3. **Renew DHCP lease (replace `eth0` with the correct interface)**  
   ```bash
   sudo dhclient -r eth0 #Removes the currently assigned ip
   sudo dhclient eth0 #Query the DHCB to assign new ip
   ```
   - Releases and renews the IP address assigned via DHCP.

4. **Flush and reset the DNS cache**  
   ```bash
   sudo systemctl restart systemd-resolved
   ```
   - Clears the local DNS cache.

5. **Check open ports and listening services**  
   ```bash
   ss -tuln
   ```
   - Displays active listening ports on the system.
---

### **Lab Summary**
In this lab, you learned how to:  
✅ Check network settings and IP addresses  
✅ Test connectivity using `ping`, `traceroute`, and `nslookup`  
✅ Troubleshoot network issues using `ip`, `dhclient`, and `ss`  
