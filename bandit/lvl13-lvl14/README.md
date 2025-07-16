Great work! Here's the full `README.md` for **Bandit Level 13 → Level 14**, clearly documenting the SSH key usage method:

---

````markdown
# Bandit Level 13 → Level 14

In this level, instead of using a password to access the next level, you are provided with a private SSH key in the file `sshkey.private`. The goal is to use this key to authenticate as `bandit14`.

---

**Connection Details:**
- Host: `localhost` *(from the Bandit server itself)*
- Port: `2220`
- Username: `bandit14`
- Authentication: `sshkey.private` (no password)

---

**Steps Taken:**

```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
ls -la

# Use the private SSH key to login as bandit14
ssh -i sshkey.private bandit14@localhost -p 2220
````

> `-i sshkey.private`: specifies the identity (private key) file for login.
> Since you're already on the Bandit server, connecting to `localhost` works directly.

---

**What I Learned:**

* How to use an SSH private key for passwordless authentication
* Secure file permissions and key-based login mechanisms
* Inter-user login from within the remote host

---

**Next Connection:**

Once logged in as `bandit14`, you're now ready to proceed to the next level directly within that shell session.

If logging in from your **local machine** instead of chaining from `bandit13`, you would first download `sshkey.private` and run:

```bash
chmod 600 sshkey.private
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```