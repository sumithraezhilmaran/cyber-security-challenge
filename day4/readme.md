# 🐧 Linux User & Permission Management Day 04 – Practice Notes

This repository contains my **Linux terminal practice notes**, focused on **users, permissions, sudo, su, and common permission errors**, along with how they were resolved.

---

## 📌 Scenario Overview

During Linux practice, I encountered multiple **permission denied** errors while:

* Creating directories in system paths
* Managing users
* Using `sudo` with non-privileged users
* Working with `pyenv`

These notes document the **errors**, **reasons**, and **solutions**.

---

## ❌ Errors Encountered & Explanation

### 1️⃣ Permission Denied (mkdir)

```bash
mkdir: cannot create directory ‘/usr/share/pyenv/versions’: Permission denied
```

**Reason:**

* `/usr/share` is a **system directory**
* Only `root` can write here

**Solution:**

```bash
sudo mkdir /usr/share/pyenv/versions
```

---

### 2️⃣ pyenv Rehash Error

```bash
pyenv: cannot rehash: /usr/share/pyenv/shims isn't writable
```

**Reason:**

* `pyenv` installed in a root-owned directory
* Normal users don’t have write permission

**Fix Options:**

* Use `sudo`
* OR install `pyenv` in user’s home directory (`~/.pyenv`)

---

### 3️⃣ Switching User Without Root Privileges

```bash
sudo -u thor -i
```

Successfully switched to user **thor**, but:

```bash
useradd hulk -m
Permission denied.
```

**Reason:**

* `thor` is NOT root
* `useradd` requires root privileges

---

### 4️⃣ sudo Not Allowed

```bash
sudo useradd hulk -m
thor is not in the sudoers file.
```

**Reason:**

* `thor` not part of `sudo` group

---

## ✅ Fix: Grant sudo Access

Switched to root using:

```bash
su -
```

Added `thor` to sudo group:

```bash
usermod -aG sudo thor
```

Verified:

```bash
groups thor
```

Output:

```text
thor : thor sudo users
```

---

## 👤 User Creation (as root)

```bash
sudo useradd hulk -m
sudo useradd spiderman -m
sudo useradd loki -m
```

* `-m` → creates home directory automatically

---

## 📂 Important Commands Used

```bash
whoami        # shows current user
pwd           # current directory
exit / logout # exit shell
Ctrl + D      # logout shortcut
cat /etc/passwd  # list all users
```

---

## 🔑 sudo vs su (Quick Notes)

```text
sudo → Super User DO
       Run a single command as root

su   → Switch User
       Switch to root shell or another user
```

Examples:

```bash
sudo apt update
su -
```

---

## 🧠 Key Learnings

* System directories require root access
* `useradd`, `usermod` are **root-only commands**
* Users must belong to the `sudo` group to use sudo
* `wheel` group does not exist on Debian/Ubuntu (used in RHEL)

---

## ✅ Status

✔ Understood Linux permissions
✔ Practiced real-world permission errors
✔ Learned proper privilege escalation

---

📌 *These notes are part of my Linux learning journey.*
