Great! This level introduces **setuid binaries** and privilege escalation within the context of a CTF challenge. Here's the complete `README.md` for **Bandit Level 19 → Level 20**, explaining the purpose and usage of the `bandit20-do` binary:

---

````markdown
# Bandit Level 19 → Level 20

This level demonstrates the concept of **setuid binaries**, allowing you to execute commands as another user—in this case, `bandit20`.

The file `bandit20-do` is a custom binary owned by `bandit20` and is designed to let `bandit19` run one command as `bandit20`. This is a controlled privilege escalation mechanism.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit19`
- Password: (from previous level)

---

### 🔐 SSH Access:

```bash
ssh bandit19@bandit.labs.overthewire.org -p 2220
````

---

### ⚙️ Exploring `bandit20-do`:

```bash
# List the file to confirm setuid permissions
ls -l

# Output:
# -r-sr-x--- 1 bandit20 bandit19 12345 Jan 01 00:00 bandit20-do
```

Note the `s` in the user execute position (`-r-sr-x---`), meaning it runs with the **privileges of its owner**, `bandit20`.

---

### 🔍 Steps Taken:

```bash
# Run the binary with a harmless command to verify access level
./bandit20-do id

# Output includes: uid=11020(bandit20)

# Use it to read the next password:
./bandit20-do cat /etc/bandit_pass/bandit20
```

This displays the password for `bandit20`.

---

**What I Learned:**

* What setuid programs are and how they work
* How to use a wrapper binary to execute limited commands as another user
* Secure privilege escalation in a sandboxed environment

---

**Output:**

```text
REDACTED
```

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit20@bandit.labs.overthewire.org -p 2220
```