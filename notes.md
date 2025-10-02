
# 📒 Linux for DevOps – Complete Notes

## 1. 🌍 How Does the Internet Work? What Are Servers?

* **Internet Basics**

  * Internet = Global network of interconnected computers using **TCP/IP protocol**.
  * Communication happens via **packets** (small chunks of data).
  * **DNS (Domain Name System)**: Converts human-friendly names (e.g., google.com) to IP addresses.
  * **Protocols**: HTTP/HTTPS, FTP, SMTP, SSH, etc.

* **Servers**

  * A **server** is a computer that provides services to other machines (clients).
  * Examples:

    * **Web Server**: Serves websites (Apache, Nginx).
    * **Database Server**: Stores/manages data (MySQL, PostgreSQL).
    * **File Server**: Shares files (Samba, NFS).
    * **Application Server**: Runs backend applications (Tomcat, Node.js).
  * In DevOps, servers are deployed on **cloud (AWS, GCP, Azure)** or **containers (Docker, Kubernetes)**.

---

## 2. 🐧 What is Linux OS? How to Setup a Linux Server?

* **Linux OS**

  * Open-source operating system based on **UNIX**.
  * Components:

    * **Kernel** (heart of OS)
    * **Shell** (CLI interface)
    * **File System** (everything is a file)
    * **Package Manager** (apt, yum, dnf)

* **Why DevOps uses Linux?**

  * Stability, security, automation (scripting), open-source tools, container support.

* **Linux Server Setup** (basic steps):

  1. Install Linux distribution (Ubuntu, CentOS, Debian, RHEL).
  2. Update packages:

     ```bash
     sudo apt update && sudo apt upgrade   # Ubuntu/Debian
     sudo yum update                       # CentOS/RHEL
     ```
  3. Create users & set permissions.
  4. Configure SSH for remote access.
  5. Install necessary services (Nginx, Apache, MySQL, etc.).
  6. Secure server (firewall, SELinux/AppArmor, fail2ban).

---

## 3. 📌 Linux Basic Commands for DevOps Engineers

* Navigation & Files:

  ```bash
  pwd        # Print current directory
  ls -l      # List files with details
  cd /path   # Change directory
  touch f1   # Create empty file
  mkdir dir  # Create directory
  rm -rf dir # Remove directory recursively
  ```
* Viewing & Editing:

  ```bash
  cat file     # Show file contents
  less file    # View file (page-wise)
  head -n 5 f  # First 5 lines
  tail -n 5 f  # Last 5 lines
  nano/vim file # Edit file
  ```
* System Info:

  ```bash
  uname -a   # Kernel details
  whoami     # Current user
  top        # Running processes
  df -h      # Disk usage
  free -m    # Memory usage
  ```

---

## 4. ⚡ Advanced Linux Commands for DevOps

* Process Management:

  ```bash
  ps aux      # List processes
  kill -9 PID # Kill process
  htop        # Interactive process viewer
  ```
* Disk/Storage:

  ```bash
  du -sh *     # Size of files/directories
  mount / umount  # Mount/unmount devices
  ```
* Networking:

  ```bash
  netstat -tulnp   # Listening ports
  ss -tulnp        # Modern replacement for netstat
  curl -I url      # Check response headers
  wget url         # Download file
  ```
* Permissions:

  ```bash
  chmod 755 file
  chown user:group file
  ```

---

## 5. 👥 Users and Groups Management in Linux

* **Users**: login accounts.
* **Groups**: collection of users with shared permissions.
* Commands:

  ```bash
  adduser devops          # Create user
  passwd devops           # Set password
  usermod -aG sudo devops # Add to group
  groups devops           # Show groups
  deluser devops          # Remove user
  ```
* **File Ownership**:

  * `ls -l` shows owner & group.
  * `chown user:group file` changes ownership.

---

## 6. 📂 File Management in Linux

* File operations:

  ```bash
  cp src dest      # Copy
  mv old new       # Move/rename
  rm file          # Remove
  ```
* File permissions:

  * `r` = read, `w` = write, `x` = execute.
  * Example:

    ```bash
    chmod 644 file   # Owner read/write, others read-only
    chmod +x script  # Add execute permission
    ```

---

## 7. 🔄 File Transfer Commands

* **scp** (secure copy):

  ```bash
  scp file user@server:/path
  scp user@server:/path/file .
  ```
* **rsync** (sync files):

  ```bash
  rsync -avz local/ user@server:/remote/
  ```
* **sftp** (secure FTP):

  ```bash
  sftp user@server
  ```

---

## 8. 🌐 Linux Networking Commands

* Check IP & network:

  ```bash
  ip a       # Show IP addresses
  ifconfig   # Legacy
  ping 8.8.8.8
  traceroute google.com
  ```
* Open ports & connections:

  ```bash
  netstat -tulnp
  ss -ltnp
  ```
* Firewall:

  ```bash
  ufw allow 22/tcp
  ufw enable
  ```

---

## 9. 🔍 Pro Linux Commands (AWK, GREP, FIND, SED)

* **grep**: search text

  ```bash
  grep "error" logfile
  grep -i "devops" file
  ```
* **awk**: process structured text

  ```bash
  awk '{print $1,$3}' file   # Print 1st and 3rd column
  ```
* **find**: locate files

  ```bash
  find / -name "*.log"
  ```
* **sed**: stream editor

  ```bash
  sed 's/error/warning/g' file   # Replace error → warning
  ```

---

## 10. 💾 Linux Volume Management

* Manage storage devices.
* Commands:

  ```bash
  lsblk       # Show disks
  fdisk -l    # Partition info
  mount /dev/sdb1 /mnt
  umount /mnt
  ```

---

## 11. 📦 LVM (Logical Volume Manager) in Linux

* **Why LVM?** Flexible storage management (resize volumes without downtime).

* Components:

  * **PV (Physical Volume)** → Actual disk/partition.
  * **VG (Volume Group)** → Pool of PVs.
  * **LV (Logical Volume)** → Usable partition for filesystems.

* Workflow:

  ```bash
  pvcreate /dev/sdb
  vgcreate my_vg /dev/sdb
  lvcreate -L 10G -n my_lv my_vg
  mkfs.ext4 /dev/my_vg/my_lv
  mount /dev/my_vg/my_lv /mnt
  ```

---
