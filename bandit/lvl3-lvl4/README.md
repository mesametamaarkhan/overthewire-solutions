Great! Here's a clean and complete `README.md` for **Bandit Level 3 → Level 4**, following the format you've been using:

---

````markdown
# Bandit Level 3 → Level 4

The goal of this level is to find the password hidden inside a file located in a subdirectory named `inhere`. The file is hidden and has a non-standard name, requiring the use of `ls -la` to reveal it.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit3`
- Password: (from previous level)

---

**Commands Used:**

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
ls -la
cd inhere
ls -la
cat ...Hiding-from-you
````

> Note: The actual file name may vary — it could be something like `.hidden`, `.pass`, or `.dotfile`. In this case, it was a file named `.hidden` (or `.Hiding-from-you`, as you described — adjust below accordingly):

```bash
cat .Hiding-from-you
```

---

**Output:**

The file contains the password for Bandit Level 4:

```text
REDACTED
```

---

**What I Learned:**

* Navigating subdirectories using `cd`
* Listing hidden files with `ls -la`
* Recognizing Unix hidden files (those starting with a dot)
* Using `cat` to read a file with a tricky or unusual name

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```