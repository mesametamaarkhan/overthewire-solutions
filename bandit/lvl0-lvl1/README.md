Got it — here's a **single, clean, complete `README.md`** for **Bandit Level 0**, without broken-out steps or headings repeated unnecessarily:

---

````markdown
# Bandit Level 0 → Level 1

This level introduces the basics of SSH and file navigation in a Linux environment. The objective is to connect to the Bandit server using SSH and read the contents of a file named `readme` in the home directory, which contains the password for the next level.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit0`
- Password: (provided on the OverTheWire site)

---

**Commands Used:**

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
cat readme
````

---

**Output:**

The `readme` file contains the password for Bandit Level 1:

```text
REDACTED
```

---

**What I Learned:**

* How to SSH into a remote server on a non-standard port
* How to read files using `cat`
* The importance of exploring the home directory for clues

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

```
