
# 📒 Linux Notes

## **Day-03 – Users & Files Management**

---

## **1️⃣ System-Level Commands**

#### `uname` – Show System Info

```bash
uname          # prints OS name
uname -a       # all system info (kernel, hostname, OS)
uname -r       # kernel version
```

#### `uptime` – System Uptime

```bash
uptime        # shows how long system has been running, load averages
```

#### `date` – Show or Set Date

```bash
date          # current date & time
date "+%Y-%m-%d %H:%M:%S"  # custom format
```

#### `who`, `whoami` – Users Info

```bash
who           # logged in users
whoami        # current user
```

#### `which` – Locate Executables

```bash
which python3   # shows path of python3 executable
```

#### `id` – Show User/Group Info

```bash
id user        # UID, GID, group memberships
```

#### `sudo` – Execute Command as Superuser

```bash
sudo apt update       # execute command with root privileges
sudo -i              # open root shell
```

#### `shutdown` – Power Off System

```bash
sudo shutdown now      # immediate shutdown
sudo shutdown -h +10   # shutdown after 10 minutes
```

#### `reboot` – Reboot System

```bash
sudo reboot
```

#### Package Managers

| Command   | Use                                    |
| --------- | -------------------------------------- |
| `apt`     | Ubuntu/Debian, install/update packages |
| `yum`     | CentOS/RHEL, older versions            |
| `dnf`     | Fedora, CentOS 8+, newer RedHat        |
| `pacman`  | Arch Linux                             |
| `portage` | Gentoo Linux                           |

---

## **2️⃣ User & Group Management Commands**

#### Create & Manage Users

```bash
sudo useradd devops      # create user
sudo passwd devops       # set password
whoami                   # current user
su - user                # switch user
sudo                     # run command as root
sudo userdel -r devops   # delete user and home dir
```

#### Create & Manage Groups

```bash
sudo groupadd devgroup           # create group
sudo gpasswd -a devops devgroup  # add user to group
sudo gpasswd -d devops devgroup  # remove user from group
sudo groupdel devgroup           # delete group
```

---

## **3️⃣ File Permission Commands**

#### `umask` – Default File Permission

* Determines **default permissions** for newly created files/directories.

```bash
umask          # current mask
umask 022      # default 755 for dirs, 644 for files
```

#### `ls -l` – List Permissions

```bash
ls -l
-rwxr-xr-- 1 user group 4096 file.txt
```

* `r` = read, `w` = write, `x` = execute
* Owner | Group | Others

#### `chmod` – Change Permissions

```bash
chmod 755 file.txt      # numeric
chmod u+x file.txt      # symbolic
chmod g-w file.txt
```

#### `chown` – Change Owner

```bash
sudo chown user file.txt
sudo chown user:group file.txt
```

#### `chgrp` – Change Group

```bash
sudo chgrp devgroup file.txt
```

---

## **4️⃣ Compression Commands**

#### `zip` – Compress Files

```bash
zip archive.zip file1 file2
unzip archive.zip
```

#### `gzip` / `gunzip` – Compress/Decompress

```bash
gzip file.txt       # creates file.txt.gz
gunzip file.txt.gz
```

#### `tar` – Archive Files

```bash
tar -cvf archive.tar dir/       # create tar archive
tar -xvf archive.tar            # extract archive
tar -czvf archive.tar.gz dir/   # gzip + tar
tar -xzvf archive.tar.gz        # extract gzip tar
```

---

## **5️⃣ File Transfer Commands**

#### `scp` – Secure Copy (SSH based)

```bash
scp file.txt user@server:/path/
scp user@server:/path/file.txt .   # copy from remote to local
```

#### `rsync` – Sync Files (Efficient)

```bash
rsync -avz local/ user@server:/remote/   # copy & sync
rsync -avz --delete local/ remote/      # delete removed files
```

* DevOps use: backups, deployments, server syncs.

---

✅ **Day-03 Notes Summary:**

* System info commands: `uname`, `uptime`, `date`, `who`, `id`
* User & group management: `useradd`, `passwd`, `groupadd`, `gpasswd`
* File permissions: `chmod`, `chown`, `chgrp`, `umask`
* Compression: `zip`, `gzip`, `tar`
* File transfer: `scp`, `rsync`

---
