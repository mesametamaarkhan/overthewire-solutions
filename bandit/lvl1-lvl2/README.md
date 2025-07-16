Great! Based on your description, here’s a clean, single-file `README.md` for **Bandit Level 1 → Level 2**, following the same format:

---

````markdown
# Bandit Level 1 → Level 2

The goal of this level is to find the password for the next level, which is stored in a file called `-` (a single dash). This file is located in the home directory. Since `-` is often interpreted as a special argument (typically meaning "stdin"), it requires special handling when used as a filename.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit1`
- Password: (from previous level)

---

**Commands Used:**

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
cat < -
OR
cat ./-
````

---

**Output:**

The file contains the password for Bandit Level 2:

```text
REDACTED
```

---

**What I Learned:**

* How to handle filenames that begin with a dash (`-`)
* How to avoid interpreting special characters by explicitly referencing the path (e.g., `./-`)
* Continued practice with SSH and basic Linux file operations

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

```
