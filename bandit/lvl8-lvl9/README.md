Great! Here's a complete and well-formatted `README.md` for **Bandit Level 8 → Level 9**, based on the method you used:

---

````markdown
# Bandit Level 8 → Level 9

The goal of this level is to identify the only line in the file `data.txt` that appears **exactly once**. All other lines occur multiple times. The unique line contains the password for the next level.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit8`
- Password: (from previous level)

---

**Commands Used:**

```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
ls -la
sort data.txt | uniq -u -c
````

> * `sort` ensures duplicate lines are grouped together.
> * `uniq -u -c` filters out lines that occur more than once and shows only unique entries with a count.

You may also simplify with:

```bash
sort data.txt | uniq -u
```

Once the unique line is identified, it is the password.

---

**Output:**

The unique line contains the password for Bandit Level 9:

```text
REDACTED
```

---

**What I Learned:**

* Using `sort` to group duplicate lines together
* Applying `uniq` with `-u` to isolate lines that appear only once
* Basic data analysis techniques using shell tools

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```