# Day 3 notes:

# 🐧 Linux User Management – My Learning Notes

This repository contains my personal notes on **Linux user management**, including user creation, password handling, permissions, and common commands.

---

## 📌 Basic Commands

### 1. Check Current User

```bash
whoami
```

---

## 👤 User Creation & Management

### 2. Add a User (Without Root)

```bash
adduser thor
```

❌ Output:

> only the root user can add users

---

### 3. Add User Using `sudo`

```bash
sudo adduser thor
```

**Sample Output:**

```text
[sudo] password for kritira:
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for thor
Full Name []: thor
Room Number []:
Work Phone []:
Home Phone []:
Other []:
Is the information correct? [Y/n] Y
```

---

## 📂 User Information Files

### 4. View `/etc/passwd`

```bash
cat /etc/passwd
```

**Sample Output:**

```text
root:x:0:0:root:/root:/usr/bin/zsh
kritira:x:1000:1000:Sumithra Ezhilmaran:/home/kritira:/usr/bin/zsh
thor:x:1001:1001:thor:/home/thor:/bin/bash
```

### 🔑 Explanation of Fields

```text
username:x:UID:GID:comment:home_directory:login_shell
```

* `x` → Password is stored in `/etc/shadow`
* `UID` → User ID
* `GID` → Group ID

---

### 5. View Password Hashes

```bash
sudo cat /etc/shadow
```

⚠️ Only root can access this file
Passwords are stored in **hashed form**

---

## ➕ Creating Users with `useradd`

### 6. Add User Using `useradd`

```bash
sudo useradd ironman
```

Check:

```bash
cat /etc/passwd
```

**Output:**

```text
ironman:x:1002:1002::/home/ironman:/bin/sh
```

---

### 7. Set Password for User

```bash
sudo passwd ironman
```

---

## 📁 Home Directory Check

```bash
cd /home
ls
```

**Output:**

```text
kritira  thor
```

❗ `ironman` home directory not visible yet.

### Show Hidden Files

```bash
ls -al
```

---

## 🔧 User Modification

### 8. `usermod` Help

️

```bash
usermod -h
```

---

### 9. Permission Issue While Accessing User Directory

❌ Error when entering:

```bash
cd thor
Permission denied
```

### Fix:

```bash
ls -ld thor
sudo -u thor -i
pwd
```

✅ Successfully entered into `thor` user.

---

## 🐚 Change User Shell

### 10. Change Shell for `ironman`

```bash
sudo usermod ironman --shell /bin/bash
```

❌ Error:

```text
thor is not in the sudoers file
```

### Solution:

Exit from `thor` and switch back to sudo user.

```bash
exit
whoami
sudo usermod ironman --shell /bin/bash
```

Verify:

```bash
getent passwd ironman
```

**Output:**

```text
ironman:x:1002:1002::/home/ironman:/bin/bash
```

---

## 🔑 Switch Users

### Incorrect:

```bash
su -ironman
```

### Correct:

```bash
sudo -i
```

✅ Successfully entered as root.

---

## 🔍 Verify Password Update

```bash
sudo cat /etc/shadow
```

---

## 📘 Help Commands

### User Creation Help

```bash
useradd -h
```

Displays all options for adding users.

---

## ✅ Summary

* Learned how users are created in Linux
* Understood `/etc/passwd` and `/etc/shadow`
* Practiced `adduser`, `useradd`, `usermod`, `passwd`
* Fixed permission and sudo issues
* Changed default shells

---


