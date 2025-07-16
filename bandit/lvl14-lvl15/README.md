Excellent! Here’s the complete and well-formatted `README.md` for **Bandit Level 14 → Level 15**, based on your process:

---

````markdown
# Bandit Level 14 → Level 15

In this level, you're provided with the password for `bandit14` and asked to connect to a **local port (30000)** using `netcat`. Once connected, you must send the `bandit14` password through the socket to retrieve the password for the next level.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit14`
- Password: (from previous level)

---

**Steps Taken:**

```bash
ssh bandit14@bandit.labs.overthewire.org -p 2220

# Connect to the local service running on port 30000
nc localhost 30000

# When prompted, paste the current level's password
````

After entering the password, the service responds with the password for Bandit Level 15.

---

**What I Learned:**

* How to use `nc` (netcat) to interact with TCP sockets
* Basic client-server communication over a port
* Sending and receiving plain text over network streams

---

**Output:**

The response from the service contains the password for Bandit Level 15:

```text
REDACTED
```

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220
```
