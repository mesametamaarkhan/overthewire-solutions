Perfect — that was a fun multi-step extraction challenge! Here's a clean, detailed `README.md` for **Bandit Level 12 → Level 13**, capturing every step you took:

---

````markdown
# Bandit Level 12 → Level 13

In this level, the password is stored in a file called `data.txt`, but it has been **repeatedly encoded and archived** using various compression and packaging formats (gzip, bzip2, tar, etc). The challenge is to unpack the file layer by layer until the password is revealed.

---

**Connection Details:**
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit12`
- Password: (from previous level)

---

**Commands Used:**

```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
ls -la

# Work in a personal temp directory
mkdir /tmp/mtk
cp data.txt /tmp/mtk
cd /tmp/mtk

# Reverse hexdump to binary
xxd -r data.txt > data
file data

# Unpack layers step by step
mv data file.gz
gzip -d file.gz

file file
mv file file.bz2
bzip2 -d file.bz2

file file
mv file file.gz
gzip -d file.gz

mv file file.tar
tar xf file.tar

file data5.bin
mv data5.bin data5.tar
tar xf data5.tar

file data6.bin
mv data6.bin data6.tar
tar xf data6.tar

file data8.bin
mv data8.bin data8.gz
gzip -d data8.gz

file data8
cat data8
````

> After the final decompression, `cat data8` reveals the password.

---

**Output:**

The final output of `cat data8` contains the password for Bandit Level 13:

```text
REDACTED
```

---

**What I Learned:**

* Using `xxd` to reverse hex dumps into binary
* Identifying file types with the `file` command
* Unpacking various archive formats: gzip, bzip2, tar
* Navigating through nested compression layers methodically

---

**Next Connection:**

Use the password above to connect to the next level:

```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```