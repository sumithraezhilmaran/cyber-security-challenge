# 🛡️ Day 2 – Shell, Terminal & System Information (Cybersecurity Challenge)

## 🔹 Shell vs Terminal (Important Concept)

* **Shell** → Interface (UI) used to interact with the **Linux kernel**
* **Terminal Emulator** → Program that lets us access the shell using keyboard & display
* Most common shell:

  * **Bash** (Bourne Again Shell)

📌 Example:

* Shell → `bash`
* Terminal → `terminal`, `console`, `xterm`

---

## 🔹 Process & Shell Identification

### Process Status

```bash
ps
```

* Shows running processes
* On Windows PowerShell → shows `pwsh`
* On Linux → shows `bash`

---

## 🔹 Root Access & Privileges

* `$` → Normal user
* `#` → Root user

### Switch to root

```bash
sudo su
```

### Set / Change root password

```bash
sudo passwd root
```

---

## 🔹 User & System Identity Commands

| Command    | Purpose                 |
| ---------- | ----------------------- |
| `whoami`   | Shows current user      |
| `id`       | Displays user identity  |
| `hostname` | Shows system hostname   |
| `pwd`      | Shows current directory |

---

## 🔹 System Information

```bash
uname
uname -r
uname -a
```

Example output:

```
Linux Kritira 6.12.38+kali-amd64 x86_64 GNU/Linux
```

---

## 🔹 Networking & System Inspection Commands

| Command    | Description                          |
| ---------- | ------------------------------------ |
| `ifconfig` | View or configure network interfaces |
| `ip`       | Modern replacement for ifconfig      |
| `netstat`  | Shows network status                 |
| `ss`       | Socket statistics                    |
| `who`      | Shows logged-in users                |
| `env`      | Displays environment variables       |
| `lsblk`    | Lists block devices                  |
| `lsusb`    | Lists USB devices                    |
| `lspci`    | Lists PCI devices                    |
| `lsof`     | Lists open files                     |

📌 **Cybersecurity relevance**:

* Network enumeration
* User monitoring
* Device discovery
* Open file investigation

---

## 🔹 Manual & Help Commands

### Manual pages

```bash
man uname
man ip
man ls
```

### Built-in help

```bash
uname --help
```

### Search commands by keyword

```bash
apropos usb
apropos compress
```

Useful when you **forget command names**.

---

## 🔹 Bash Prompt Special Characters (PS1)

### Table 1: Prompt Symbols

| Symbol         | Description       |
| -------------- | ----------------- |
| `\d`           | Date (Mon Feb 6)  |
| `\D{%Y-%m-%d}` | Date (YYYY-MM-DD) |
| `\H`           | Full hostname     |
| `\j`           | Number of jobs    |
| `\n`           | New line          |
| `\r`           | Carriage return   |
| `\s`           | Shell name        |
| `\t`           | Time (24-hour)    |
| `\T`           | Time (12-hour)    |
| `\@`           | Time              |
| `\u`           | Username          |
| `\w`           | Current directory |

---

## 🔹 Command Summary Table

### Table 2: Commands Overview

| Command    | Description               |
| ---------- | ------------------------- |
| `whoami`   | Displays current username |
| `id`       | Returns user identity     |
| `hostname` | Shows system hostname     |
| `uname`    | System & OS info          |
| `pwd`      | Current directory         |
| `ifconfig` | Network interfaces        |
| `ip`       | Network configuration     |
| `netstat`  | Network status            |
| `ss`       | Socket information        |
| `ps`       | Process status            |
| `who`      | Logged-in users           |
| `env`      | Environment variables     |
| `lsblk`    | Block devices             |
| `lsusb`    | USB devices               |
| `lspci`    | PCI devices               |
| `lsof`     | Open files                |

---

## 🔐 Cybersecurity Takeaways (Day 2)

* Shell knowledge helps understand **command execution**
* Root access (`sudo`, `su`) is critical in attacks & defense
* System info commands help in:

  * Enumeration
  * Incident response
  * Privilege escalation
* `man` & `apropos` are essential **self-learning tools**

---

## ✅ Day 2 Status

**✔ Completed (Hands-on)**

---
