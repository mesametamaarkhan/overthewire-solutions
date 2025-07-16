Awesome, you're moving fast! Here's the complete and polished `README.md` for **Bandit Level 15 → Level 16**:

---

````markdown
# Bandit Level 15 → Level 16

In this level, you're required to connect to a service running on **port 30001**, but this time the connection must be made over **SSL**. Once connected, you provide the password for `bandit15`, and the service responds with the password for the next level.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit15`
- Password: (from previous level)

---

**Steps Taken:**

```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220

# View the current level's password (optional, if not stored locally)
cat /etc/bandit_pass/bandit15

# Connect to the SSL service on port 30001 using ncat
ncat --ssl localhost 30001

# When prompted, paste the password for bandit15
````

After submitting the password, the service returns the password for `bandit16`.

---

**What I Learned:**

* Using `ncat` (netcat with SSL support) to connect securely to local services
* The difference between plain TCP and SSL-encrypted socket connections
* Secure communication basics in CTF challenges

---

**Output:**

The SSL service outputs the password for Bandit Level 16:

```text
REDACTED
```

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit16@bandit.labs.overthewire.org -p 2220
```