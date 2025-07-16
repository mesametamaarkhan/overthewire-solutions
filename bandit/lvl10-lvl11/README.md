Awesome! Here's the full, clean `README.md` for **Bandit Level 10 → Level 11**, based on your process:

---

````markdown
# Bandit Level 10 → Level 11

In this level, the password for the next level is stored in a file called `data.txt`, but it’s encoded using **Base64**. The goal is to decode the file to reveal the password.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit10`
- Password: (from previous level)

---

**Commands Used:**

```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
ls -la
strings data.txt | base64 -d
````

> * `strings` extracts the readable portion of the file (if needed).
> * `base64 -d` decodes the Base64-encoded password.

If the file is **entirely** Base64-encoded and doesn't contain any binary junk, you can decode directly:

```bash
base64 -d data.txt
```

---

**Output:**

The decoded result reveals the password for Bandit Level 11:

```text
REDACTED
```

---

**What I Learned:**

* How to decode Base64-encoded data using `base64 -d`
* How to identify encoded formats based on structure (e.g., trailing `=`)
* More efficient ways to extract information from encoded or binary files

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```