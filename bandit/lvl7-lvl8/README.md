Awesome — here’s the complete and clean `README.md` for **Bandit Level 7 → Level 8**, based on your workflow:

---

````markdown
# Bandit Level 7 → Level 8

The goal of this level is to find the password hidden inside a file named `data.txt`. The password is embedded within the file, so regular text viewing commands like `cat` aren't sufficient — instead, we extract printable strings and search for a specific keyword.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit7`
- Password: (from previous level)

---

**Commands Used:**

```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
ls -la
strings data.txt | grep "millionth"
````

> `strings` extracts printable characters from binary or mixed-content files.
> `grep` filters output to only show lines containing the word "millionth".

---

**Output:**

The line containing `"millionth"` includes the password for Bandit Level 8:

```text
REDACTED
```

---

**What I Learned:**

* How to use `strings` to extract human-readable content from binary files
* Efficient filtering with `grep`
* A common CTF technique: hiding secrets in large or noisy files

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
```