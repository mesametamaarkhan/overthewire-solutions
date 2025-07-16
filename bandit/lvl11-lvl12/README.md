Great! Here's the full `README.md` for **Bandit Level 11 → Level 12**, based on your description:

---

````markdown
# Bandit Level 11 → Level 12

In this level, the password is stored in `data.txt`, but it has been encoded using **ROT13** — a simple letter substitution cipher that shifts characters 13 positions in the alphabet. Decoding it reveals the password for the next level.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit11`
- Password: (from previous level)

---

**Commands Used:**

```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
cat data.txt
````

> Copy the output text from `data.txt` and decode it using a ROT13 decoder.
> This can be done online (e.g., [rot13.com](https://rot13.com)) or with a local command:

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

---

**Output:**

The decoded ROT13 string is the password for Bandit Level 12:

```text
REDACTED
```

---

**What I Learned:**

* How ROT13 works as a simple Caesar cipher
* Using `tr` to decode ROT13 directly in the terminal
* Recognizing common encoding techniques used in CTF challenges

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
```