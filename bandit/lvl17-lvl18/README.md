Nice! This level is all about comparing files and spotting subtle differences. Here's the complete and clean `README.md` for **Bandit Level 17 → Level 18**:

---

````markdown
# Bandit Level 17 → Level 18

In this level, you're given two files: `passwords.old` and `passwords.new`. The goal is to compare them and find the difference, which reveals the password for the next level.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit17`
- Authentication: Private key (`bandit17.key` from previous level)

---

### 🔐 SSH Access:

```bash
ssh -i bandit17.key bandit17@bandit.labs.overthewire.org -p 2220
````

---

### 🔍 Steps Taken:

```bash
# Move to home directory where the files are stored
cd /home/bandit17

# Compare the two password files
diff --normal passwords.old passwords.new
```

The output shows the lines that differ between the files. The **password for Bandit Level 18** is the changed line found at the end of the diff output.

---

**What I Learned:**

* Using `diff` to compare file contents
* Understanding simple change detection between versions of a file
* Navigating user home directories and inspecting file deltas

---

**Output:**

The last line from the `diff` result is the password:

```text
REDACTED
```

---

**Next Connection:**

Use the password above to connect to Bandit Level 18:

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220
```