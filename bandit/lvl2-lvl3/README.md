Perfect — here’s a complete `README.md` for **Bandit Level 2 → Level 3**, based on what you described:

---

````markdown
# Bandit Level 2 → Level 3

The objective of this level is to find a file that contains spaces in its name. This file is hidden in the home directory and contains the password for the next level. Because of the spaces, the filename needs to be handled with care (quoted or escaped).

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit2`
- Password: (from previous level)

---

**Commands Used:**

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
ls -la
cat "spaces in this filename"
````

---

**Output:**

The file contains the password for Bandit Level 3:

```text
REDACTED
```

---

**What I Learned:**

* How to identify hidden or unusually named files using `ls -la`
* How to handle filenames with spaces using quotes
* Deeper familiarity with shell syntax and file interaction

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```
