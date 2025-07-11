
# 🧪 Hands-On Lab: Network Troubleshooting and Discovery Tools in Linux

## 🎯 Objective
Learn to use common network troubleshooting tools to diagnose, monitor, and discover network issues or configurations.

---

## 🔧 Prerequisites
- A Linux system with internet access
- Basic knowledge of the terminal and sudo privileges
- Ensure the tools (`ping`, `traceroute`, `netstat` or `ss`, `dig`, `tcpdump`, and `nmap`) are installed

---

## 🛠️ Tools and Exercises

### 1. `ping` – Test Connectivity
**Objective:** Check if a remote host is reachable.

```bash
ping google.com
```

**Use Case:**
Verify if the DNS is resolving and the network path to the internet is functional.

---

### 2. `traceroute` – Path Tracing
**Objective:** Identify the route packets take to reach a host.

```bash
traceroute google.com
```

**Use Case:**
Identify latency points or dropped hops in a multi-hop path.

---

### 3. `netstat` or `ss` – Network Socket Statistics
**Objective:** View open ports and established connections.

```bash
sudo netstat -tulnp  # or
sudo ss -tulnp
```

**Use Case:**
Check which services are listening and what connections are established on the server.

---

### 4. `dig` – DNS Lookup Tool
**Objective:** Query DNS servers for domain name resolution.

```bash
dig example.com
```

**Use Case:**
Diagnose DNS resolution failures or propagation issues.

---

### 5. `tcpdump` – Network Packet Capture
**Objective:** Capture and analyze network traffic.

```bash
sudo tcpdump -i eth0 port 80
```

**Use Case:**
Monitor HTTP traffic to troubleshoot connectivity or inspect anomalies.

**Note:** Replace `eth0` with the correct interface name (`ip a` to list).

---

### 6. `nmap` – Network Mapper
**Objective:** Discover hosts and services on a network.

```bash
nmap -sS -p 22,80,443 192.168.1.0/28
```

**Use Case:**
Scan a subnet to identify active hosts and services (e.g., SSH, HTTP, HTTPS).

---

## 🧹 Cleanup (for tcpdump and nmap logs if saved)
```bash
sudo rm tcpdump_capture.pcap
```

---

## 🧠 Review Questions
1. How does `ping` help detect packet loss?
2. When would you prefer `ss` over `netstat`?
3. How can `dig` help diagnose DNS misconfigurations?
4. What precautions should be taken when using `tcpdump` or `nmap` on a production network?
5. What information can `nmap` provide about remote systems?

---