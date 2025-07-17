Perfect! This level introduces **inter-process communication** via networking between two terminals using `nc` (netcat) and a custom binary (`suconnect`). Here's a clean and complete `README.md` for **Bandit Level 20 → Level 21**:

---

````markdown
# Bandit Level 20 → Level 21

This level focuses on using **network sockets** for local inter-process communication. You're provided with a binary (`suconnect`) that connects to a port on `localhost`, expecting to receive the password for `bandit20`. When it does, it authenticates and reveals the password for `bandit21`.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit20`
- Password: (from previous level)

---

### 🖥️ Dual Terminal Setup

You’ll need to open **two terminal sessions** logged in as `bandit20`.

---

### 📥 Terminal 1 — Start a Netcat Listener

Choose any high-numbered port (e.g., `4444`), and run:

```bash
cat /etc/bandit_pass/bandit20 | nc -l 4444
````

This sends the password to any process that connects to port `4444`.

---

### 📤 Terminal 2 — Connect Using suconnect

Run the following using the same port as above:

```bash
./suconnect 4444
```

This program connects to `localhost:4444`, receives the password from Terminal 1, and prints the password for `bandit21`.

---

**What I Learned:**

* How to use `nc` to create local TCP listeners
* How binaries can perform local socket communication
* Inter-process networking on the same machine using loopback (`localhost`)
* Scripting and coordination between multiple terminals

---

**Output (from Terminal 1):**

```text
REDACTED
```

This is the password for `bandit21`.

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit21@bandit.labs.overthewire.org -p 2220
```