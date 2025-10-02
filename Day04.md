
# 📒 Linux Notes

## **Day-04 – Networking Commands**

---

## **1️⃣ Basic Network Utilities**

### `ping` – Test Connectivity

```bash
ping google.com          # check if host is reachable
ping -c 4 google.com     # send 4 packets and stop
```

* Uses **ICMP** protocol to check connectivity & latency.
* DevOps use: Monitor server availability.

---

### `netstat` – Network Statistics

```bash
netstat -tulnp           # show listening TCP/UDP ports
netstat -i               # network interfaces
```

* Modern alternative: `ss`

---

### `ifconfig` – Network Interface Config

```bash
ifconfig                # show IP, netmask, MAC address
ifconfig eth0 up        # enable interface
ifconfig eth0 down      # disable interface
```

* Legacy command; replaced by `ip` in newer Linux.

---

### `ip` – Modern Network Tool

```bash
ip addr show            # show IP addresses
ip link show            # show interfaces
ip route show           # show routing table
```

---

### `iwconfig` – Wireless Interfaces

```bash
iwconfig wlan0          # show wireless info
```

* Useful for Wi-Fi configuration.

---

### `ss` – Socket Statistics (Modern `netstat`)

```bash
ss -tuln                # listening TCP/UDP ports
ss -s                   # summary
```

---

### `arp` – Address Resolution Protocol Table

```bash
arp -a                  # show IP → MAC mappings
```

---

### `hostname` – Show or Set Hostname

```bash
hostname                # show current hostname
hostnamectl set-hostname server1   # set hostname
```

---

### `nslookup` – DNS Lookup

```bash
nslookup google.com
```

* Resolves domain names to IPs and vice versa.

---

### `dig` – DNS Query

```bash
dig google.com
dig +short google.com    # only IP
```

* More advanced than `nslookup`.

---

### `telnet` – Test Port Connectivity

```bash
telnet google.com 80
```

* Check if specific port is open.

---

### `nc` (Netcat) – TCP/UDP Connections

```bash
nc -zv server 22          # check if port 22 is open
nc -l 1234                # listen on port 1234
```

* Can be used for testing and simple client-server scripts.

---

### `whois` – Domain Info Lookup

```bash
whois google.com
```

* Provides domain registration info.

---

### `ifplugstatus` – Check Cable Status

```bash
ifplugstatus eth0
```

* Shows if ethernet cable is connected.

---

### `traceroute` vs `tracepath`

* `traceroute google.com` → Shows all hops packets take to reach host.
* `tracepath google.com` → Similar, no root required.

---

### `mtr` – Network Diagnostic Tool

```bash
mtr google.com
```

* Combines **ping + traceroute** for live network stats.

---

## **2️⃣ Advanced Network Utilities**

### `route` – Show Routing Table

```bash
route -n
```

* Shows default gateway, routes.

---

### `nmap` – Network Scan / Port Scan

```bash
nmap 192.168.1.1
nmap -p 22-80 192.168.1.0/24
```

* DevOps use: Security & network audits.

---

### `wget` – Download Files from Web

```bash
wget https://example.com/file.zip
wget -O newfile.zip https://example.com/file.zip
```

### `curl` vs `wget`

| Feature    | curl                       | wget                    |
| ---------- | -------------------------- | ----------------------- |
| Protocols  | HTTP, HTTPS, FTP, SMTP     | HTTP, HTTPS, FTP        |
| Resume     | Limited                    | Yes, easy               |
| Output     | stdout by default          | file by default         |
| DevOps Use | API testing, HTTP requests | Download files, scripts |

---

### `watch` – Monitor Command Output

```bash
watch -n 2 df -h
```

* Runs command every N seconds, e.g., monitor disk usage.

---

### `iptables` – Firewall Rules

```bash
sudo iptables -L          # list rules
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
sudo iptables -D INPUT 1   # delete rule
```

* Configure packet filtering & security policies.

---

✅ **Day-04 Summary:**

* **Connectivity:** `ping`, `telnet`, `nc`
* **DNS:** `nslookup`, `dig`
* **Interfaces/IP:** `ifconfig`, `ip`, `iwconfig`, `ss`, `arp`
* **Routing:** `route`, `traceroute`, `tracepath`, `mtr`
* **Network monitoring:** `watch`, `nmap`, `iptables`, `hostname`
* **File transfer/download:** `wget`, `curl`

---
