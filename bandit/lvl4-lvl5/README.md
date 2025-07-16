Perfect — here's a clean and complete `README.md` for **Bandit Level 4 → Level 5**, matching your process and formatting style:

---

````markdown
# Bandit Level 4 → Level 5

The objective of this level is to find the only human-readable file (ASCII text) in a directory containing several files, all of which are located in the `inhere` subdirectory.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit4`
- Password: (from previous level)

---

**Commands Used:**

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
ls -la
cd inhere
ls -la
find . -type f | xargs file
cat ./-file07
````

> The `file` command identifies the type of each file, and `xargs` passes the results through. Only one file contains **ASCII text**, which likely holds the password.

---

**Output:**

The human-readable file contains the password for Bandit Level 5:

```text
REDACTED
```

---

**What I Learned:**

* Using `find` to locate all regular files recursively
* Leveraging `file` to determine file types
* Combining commands with `xargs` to analyze multiple files
* Reading a file with a leading dash in its name by prefixing it with `./`

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
```