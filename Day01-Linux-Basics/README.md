# 🛡️ Day 1 – Linux & Kali Linux Fundamentals (Cybersecurity Challenge)

## 🔹 Linux & Kali Basics

* **Linux** → Kernel (open-source, fast, secure)
* **Kali Linux** → Operating System & security-focused Linux distribution (flavour)

---

## 🔹 Basic Linux Commands

| Command  | Purpose                                                   |
| -------- | --------------------------------------------------------- |
| `pwd`    | Shows current directory                                   |
| `ls`     | Lists files and folders                                   |
| `cd`     | Change directory                                          |
| `cd ..`  | Go back one directory                                     |
| `cd /`   | Go to root directory                                      |
| `clear`  | Clear terminal screen                                     |
| `whoami` | Show current username                                     |
| `sudo`   | Execute command with root privileges (request permission) |

---

## 🔹 File & Directory Commands

| Command           | Description                    |
| ----------------- | ------------------------------ |
| `cat file`        | Display file content           |
| `cp file newfile` | Copy files                     |
| `which ls`        | Show command binary location   |
| `unalias ls`      | Fix alias issue for `which ls` |
| `ls -ld folder`   | Check folder permissions       |
| `chmod +x folder` | Change execute permission      |

---

## 🔹 Linux Filesystem (Root `/`)

From root (`/`), important directories:

| Directory   | Purpose               |
| ----------- | --------------------- |
| `/bin`      | Essential binaries    |
| `/sbin`     | System admin binaries |
| `/usr/bin`  | User binaries         |
| `/usr/sbin` | Admin binaries        |
| `/boot`     | Bootloader & kernel   |
| `/lib`      | Shared libraries      |
| `/home`     | User directories      |
| `/root`     | Root user home        |
| `/dev`      | Device files          |
| `/etc`      | Configuration files   |
| `/tmp`      | Temporary files       |
| `/var`      | Logs & variable data  |
| `/media`    | Auto-mounted USB      |
| `/mnt`      | Manual mount point    |

---

## 🔹 Important Observations (Hands-on)

* `/usr/local` → Similar to `/bin` & `/sbin`, used for **custom programs**
* `/var/log` → Critical for **log analysis & forensics**
* `/dev/sda` → Physical hard disk
* `/dev/vda` → Virtual disk (may not exist on all systems)
* Accessing `/root`:

  ```bash
  sudo ls -la /root
  ```

---

## 🔹 Permission & Access Testing

```bash
cd /home
ls
cd superben
```

❌ Permission denied → Fixed using:

```bash
ls -ld superben
sudo chmod +x superben
cd superben
```

👉 This demonstrates **Linux permission control**, a key security concept.

---

## 🔹 Network Configuration File

```bash
cd /etc
sudo cat interfaces
```

* Network settings are often modified here
* Misconfigurations can cause **network vulnerabilities**

---

## 🔹 User Management (Security Critical)

### Delete a User

```bash
whoami
id username
sudo userdel -r username
id username
ls /home
```

### Create a User

```bash
sudo useradd username
sudo passwd username
```

---

## 🔐 Cybersecurity Takeaways (Day 1)

* Linux permissions protect sensitive data
* Logs live in `/var/log`
* Attackers often target:

  * `/etc` (misconfigurations)
  * `/tmp` (persistence)
  * `/bin` & `/sbin` (privilege escalation)
* User management mistakes = **security risks**

---

### Permission Issue & Fix
![Permission denied fix](Day01-Linux-Basics
/permission-denied-fix.png)



