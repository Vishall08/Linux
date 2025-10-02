
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


---

### 📂 File & Directory Commands

#### 1. `ls` – List Files & Directories

```bash
ls         # list files in current dir
ls -l      # long listing with permissions, owner, size, time
ls -a      # show hidden files
ls -lh     # human-readable sizes
```

---

#### 2. `cd` – Change Directory

```bash
cd /etc         # go to /etc
cd ~            # go to home directory
cd -            # go back to previous directory
```

---

#### 3. `pwd` – Print Working Directory

```bash
pwd   # show current directory path
```

---

#### 4. `mkdir` – Make Directory

```bash
mkdir devops
mkdir -p /opt/projects/devops   # create nested directories
```

---

#### 5. Delete Directories & Files (`rm`, `rmdir`, `-r`)

```bash
rm file.txt        # delete file
rm -r dir/         # delete directory recursively
rm -rf dir/        # force delete (⚠ dangerous)
rmdir emptydir     # remove empty directory only
```

---

#### 6. `cat`, `zcat` – Show File Contents

```bash
cat file.txt              # show file contents
cat file1 file2 > all.txt # merge files
zcat file.gz              # view compressed file without extracting
```

---

#### 7. `touch` – Create Empty File or Update Timestamp

```bash
touch notes.txt   # create file
touch -t 202510021230 file.txt   # set custom timestamp
```

---

#### 8. `head` – View First Lines of File

```bash
head file.txt           # first 10 lines
head -n 5 file.txt      # first 5 lines
```

---

#### 9. `tail`, `tail -f` – View Last Lines of File

```bash
tail file.txt           # last 10 lines
tail -n 20 file.txt     # last 20 lines
tail -f logfile.log     # live log monitoring (useful in DevOps)
```

---

#### 10. `less`, `more` – View File (Page-Wise)

```bash
less file.txt   # scroll with ↑ ↓ / search
more file.txt   # similar but limited
```

---

#### 11. `cp` – Copy Files/Directories

```bash
cp file1 file2              # copy file
cp -r dir1 dir2             # copy directory
cp -u src.txt dest.txt      # copy only if newer
```

---

#### 12. `mv` – Move or Rename

```bash
mv old.txt new.txt     # rename
mv file.txt /tmp/      # move to /tmp/
```

---

#### 13. `wc` – Word/Line Count

```bash
wc file.txt      # lines words bytes
wc -l file.txt   # count lines
wc -w file.txt   # count words
```

---

#### 14. `vi` Editor (Unix/Linux Text Editor)

* **Modes**:

  * Command mode (default).
  * Insert mode (`i`, `a`, `o`).
  * Visual mode.
* **Basic Commands**:

  ```
  i      → insert
  :w     → save
  :q     → quit
  :wq    → save & quit
  :q!    → quit without saving
  dd     → delete line
  yy     → copy line
  p      → paste
  /word  → search
  ```

👉 Used for editing configs (`/etc/hosts`, `nginx.conf`, etc.).

---

#### 15. Links: `ln` (Hard & Soft Link)

* **Hard Link**: Direct pointer to file data. Survives if original deleted.

```bash
ln file1 file2   # create hard link
```

* **Soft Link (Symbolic)**: Shortcut to original. Breaks if original deleted.

```bash
ln -s file1 file_link
```

---

#### 16. `cut` – Extract Columns/Text

```bash
cut -d':' -f1 /etc/passwd   # get usernames
cut -c1-5 file.txt          # first 5 characters
```

---

#### 17. `tee` – Output to File & Screen

```bash
ls -l | tee files.txt       # save & show output
echo "log" | tee -a log.txt # append
```

---

#### 18. `sort` – Sort Data

```bash
sort file.txt         # alphabetical
sort -n numbers.txt   # numeric
sort -r file.txt      # reverse order
```

---

#### 19. `clear` – Clear Screen

```bash
clear
```

---

#### 20. `diff` – Compare Files

```bash
diff file1 file2       # show line differences
```

---

### 🔑 Login Related

#### 21. `ssh` – Remote Login

```bash
ssh user@host           # connect to remote server
ssh -i key.pem user@ip  # use private key
```

---

### 💾 Disk Usage

#### 22. `df` – Disk Free Space

```bash
df -h   # human-readable disk usage
```

#### 23. `du` – Directory/File Size

```bash
du -sh *   # sizes of files/dirs in current folder
du -sh /var/log
```

---

### ⚙️ Process Management

#### 24. `ps` – Process Status

```bash
ps          # processes of current shell
ps aux      # all processes
ps -ef | grep nginx
```

---

#### 25. `top` – Live Process Viewer

```bash
top    # interactive CPU/memory usage
htop   # better version (if installed)
```

---

#### 26. `fuser` – Show Process Using File/Port

```bash
fuser filename
fuser -v /var/log/syslog
fuser -k 8080/tcp    # kill process using port 8080
```

---

#### 27. `kill` – Kill Process

```bash
kill -9 PID     # force kill
kill -15 PID    # terminate gracefully
```

---

#### 28. `nohup` – Run Process in Background

```bash
nohup ./script.sh &
```

👉 Useful in servers to keep scripts running after logout.

---

#### 29. `free` – Memory Usage

```bash
free -h   # total, used, free memory
```

---

#### 30. `vmstat` – System Performance

```bash
vmstat 2 5   # report every 2 sec, 5 times
```

Shows CPU, memory, IO stats → helpful in performance monitoring.

---

