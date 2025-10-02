
# 📒 Linux Notes

## **Day-02 – Introduction of Linux**

---

### 🐧 1. What is Linux? (Introduction to Linux OS)

* **Linux** is an **open-source, UNIX-like operating system**.
* It was created by **Linus Torvalds** in 1991.
* Core features:

  * Free and open-source (GPL license).
  * Multi-user, multitasking, and secure.
  * Widely used in **servers, cloud, DevOps, embedded systems, and mobile (Android)**.
* **Why DevOps uses Linux?**

  * Most tools (Docker, Kubernetes, Jenkins, Ansible) are built for Linux.
  * High stability, security, and automation with shell scripting.

---

### 💾 2. How to Install Linux?

* Choose a **Linux distribution (distro)**:

  * Popular: **Ubuntu, Debian, CentOS, RHEL, Fedora**.
* Installation options:

  1. **Dual boot** (Linux + Windows on same PC).
  2. **Virtual Machine** (VMware, VirtualBox).
  3. **Cloud Instance** (AWS EC2, GCP, Azure).
  4. **Containers** (Docker images).
* Steps (example for Ubuntu):

  1. Download **ISO image** from official site.
  2. Create bootable USB (using Rufus/Etcher).
  3. Boot system → Install Linux.
  4. Partition disk & setup username/password.

---

### 🪟 3. Difference Between Linux and Windows

| Feature       | Linux                                    | Windows                                  |
| ------------- | ---------------------------------------- | ---------------------------------------- |
| Source        | Open-source                              | Closed-source                            |
| Cost          | Free                                     | Paid license                             |
| Security      | Very secure                              | More vulnerable to viruses               |
| Customization | Highly customizable                      | Limited                                  |
| Command Line  | Strong (bash/shell)                      | Limited (cmd/PowerShell)                 |
| Usage         | Servers, cloud, DevOps, mobile (Android) | Personal PCs, gaming, enterprise desktop |

👉 DevOps engineers mostly use **Linux** because of automation, servers, and open-source tools.

---

### 🌐 4. Software Remote Location Server Tools

* Tools to **remotely access Linux servers**:

  * **SSH (Secure Shell)** → `ssh user@server`
  * **PuTTY** → SSH client for Windows.
  * **WinSCP** → Transfer files via SCP/SFTP.
  * **MobaXterm** → SSH + file transfer + terminal.
  * **Remote Desktop (XRDP, VNC)** for GUI-based access.

---

### ⚙️ 5. What are Kernel, Bootloader, and Shell?

* **Kernel**

  * Core of Linux.
  * Manages hardware, memory, processes.
  * Acts as a bridge between hardware & user applications.
* **Bootloader**

  * Program that loads the Linux kernel into memory during startup.
  * Examples: GRUB, LILO.
* **Shell**

  * Interface between user and kernel.
  * Types:

    * **Bash (Bourne Again Shell)** – default in most distros.
    * Zsh, Ksh, Fish.
  * Allows command execution & scripting.

---

### 🖥 6. Desktop Environment

* A **desktop environment (DE)** provides a **GUI interface** on top of Linux.
* Examples:

  * **GNOME** (Ubuntu default).
  * **KDE Plasma** (lightweight, customizable).
  * **XFCE, LXDE** (for low-resource systems).
* Servers usually run **without GUI (headless mode)** to save resources.

---

### 🏗 7. Linux System Architecture

* **Hardware** → Physical resources (CPU, memory, disk).
* **Kernel** → Manages hardware.
* **Shell** → Command-line interpreter.
* **System Libraries** → Functions that apps use to interact with kernel.
* **User Applications** → Software like browsers, editors, servers.

📌 Diagram (textual):

```
+----------------------+
|   User Applications  |
+----------------------+
|   System Libraries   |
+----------------------+
|       Shell          |
+----------------------+
|       Kernel         |
+----------------------+
|      Hardware        |
```

---

### 🔍 8. Information About Hardware (Linux Commands)

* `uname -a` → System info.
* `lscpu` → CPU details.
* `free -h` → Memory usage.
* `lsblk` → Block devices (disks, partitions).
* `df -h` → Disk usage.
* `lshw` → Detailed hardware info.

---

### 📂 9. Linux File System

* Linux treats **everything as a file** (including devices).
* **Hierarchy (FHS – Filesystem Hierarchy Standard):**

  * `/` → Root directory.
  * `/bin` → Essential binaries (commands).
  * `/etc` → Config files.
  * `/home` → User directories.
  * `/var` → Logs, variable data.
  * `/tmp` → Temporary files.
  * `/dev` → Device files.
  * `/proc` → Process info.
  * `/usr` → User-installed programs.

---

### 🆚 10. Difference Between Linux and Unix

| Feature   | Linux                           | Unix                       |
| --------- | ------------------------------- | -------------------------- |
| Creator   | Linus Torvalds (1991)           | AT&T Bell Labs (1970s)     |
| License   | Open-source (GPL)               | Mostly proprietary         |
| Cost      | Free                            | Paid (HP-UX, AIX, Solaris) |
| Usage     | Servers, cloud, DevOps, Android | Legacy enterprise systems  |
| Community | Huge support                    | Limited, vendor-based      |

---

### ⚡ 11. States of Processes in Linux

Processes in Linux go through different **states**:

* **Running (R)** → Currently executing.
* **Sleeping (S)** → Waiting for an event (most common).
* **Uninterruptible Sleep (D)** → Waiting for I/O, cannot be killed easily.
* **Stopped (T)** → Suspended by a signal (e.g., Ctrl+Z).
* **Zombie (Z)** → Process finished but still in process table (waiting for parent cleanup).

👉 Commands to check:

```bash
ps aux
top
htop
```

---
