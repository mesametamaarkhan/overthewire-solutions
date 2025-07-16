Perfect — this was a clever level where you had to bypass `.bashrc` sabotage. Here's the complete and professional `README.md` for **Bandit Level 18 → Level 19**, including an explanation of the need for a forced shell:

---

````markdown
# Bandit Level 18 → Level 19

In this level, logging in as `bandit18` appears to immediately log you out. This is due to a modified `.bashrc` file that forcibly exits your session. To bypass this, you need to invoke a shell directly using `ssh` and avoid triggering the default login shell.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit18`
- Password: (from previous level)

---

### 🔐 Bypassing `.bashrc` with a Forced Shell:

```bash
ssh -t bandit18@bandit.labs.overthewire.org -p 2220 /bin/sh
````

* The `-t` flag forces pseudo-terminal allocation (required to interact with the shell).
* The `/bin/sh` at the end **overrides the default login shell**, preventing the execution of `.bashrc`.
* This lets you bypass the auto-logout behavior and remain in the session.

---

### 💡 Why This Works:

The `.bashrc` file is executed when a **bash shell** is started. In this level, it was altered to immediately run `exit`, logging you out as soon as you connect.

By forcing the SSH command to run `/bin/sh` instead of the default `bash`, and combining it with `-t` to enable interactive input, you avoid triggering `.bashrc` and remain in control of your session.

---

### 🔍 Steps Taken:

```bash
# Login using a forced shell
ssh -t bandit18@bandit.labs.overthewire.org -p 2220 /bin/sh

# View the password file for the next level
cat /etc/bandit_pass/bandit18
```

---

**What I Learned:**

* How `.bashrc` can affect login behavior
* How to bypass user shell configuration issues by overriding the shell on SSH login
* Use of `ssh -t` and custom shell paths to retain session access

---

**Output:**

```text
REDACTED
```

---

**Next Connection:**

Use the retrieved password to connect to the next level:

```bash
ssh bandit19@bandit.labs.overthewire.org -p 2220
```