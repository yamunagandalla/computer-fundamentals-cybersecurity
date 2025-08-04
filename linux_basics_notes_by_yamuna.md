# 🐧 Linux Basic Commands – Notes by Yamuna

These are beginner-friendly notes to understand and use basic Linux commands. Perfect for anyone starting out with the terminal!

---

##  1. File & Directory Commands

| Command        | Purpose                           | Example                        |
|---------------|-----------------------------------|--------------------------------|
| `pwd`         | Show current directory            | `pwd`                          |
| `ls`          | List files                        | `ls`                           |
| `ls -l`       | List with details                 | `ls -l`                        |
| `ls -a`       | List all files (including hidden) | `ls -a`                        |
| `cd folder`   | Change directory                  | `cd Documents`                 |
| `cd ..`       | Go back one folder                | `cd ..`                        |
| `cd ~`        | Go to home directory              | `cd ~`                         |
| `clear`       | Clear the terminal screen         | `clear`                        |
| `mkdir name`  | Create a new folder               | `mkdir test`                   |
| `rmdir name`  | Delete empty folder               | `rmdir test`                   |

---

##  2. File Operations

| Command                | Purpose                             | Example                                |
|------------------------|-------------------------------------|----------------------------------------|
| `touch file.txt`       | Create new file                     | `touch myfile.txt`                     |
| `rm file.txt`          | Delete a file                       | `rm notes.txt`                         |
| `rm -r folder`         | Delete folder with contents         | `rm -r myfolder`                       |
| `mv old new`           | Rename or move file/folder          | `mv old.txt new.txt`                   |
| `cp source dest`       | Copy a file                         | `cp a.txt b.txt`                       |
| `cp -r folder1 folder2`| Copy a folder and contents          | `cp -r docs backup_docs`               |

---

##  3. Viewing File Content

| Command         | Purpose                      | Example              |
|-----------------|------------------------------|----------------------|
| `echo`          | Print text or variable       | `echo "Hello"`       |
| `cat file.txt`  | Show all content             | `cat notes.txt`      |
| `more file.txt` | View large file (paged)      | `more notes.txt`     |
| `less file.txt` | Advanced file viewer         | `less notes.txt`     |

---

##  4. File Permissions

From command `ls -l`, output like:
```
-rw-r--r-- 1 user group 1024 Aug 3 file.txt
```

| Part         | Meaning                             |
|--------------|-------------------------------------|
| `-rw-r--r--` | File permissions                    |
| `user`       | Owner of the file                  |
| `group`      | Group that can access the file     |
| `1024`       | File size in bytes (1 KB)          |

###  Permissions Meaning

| Symbol | Meaning    |
|--------|------------|
| `r`    | Read       |
| `w`    | Write      |
| `x`    | Execute    |
| `-`    | No permission |

Permission split:
- `rw-` → Owner can read/write
- `r--` → Group can read
- `r--` → Others can read

---

##  5. What is `.bashrc`?

- `.bashrc` is a **hidden setup file** in your home directory.
- It runs every time you open a new terminal.
- You can add **aliases** (shortcuts) or commands inside it.

###  Example:

```bash
alias hi='echo Hello, Yamuna!'
```

After adding:
```bash
source ~/.bashrc
```
Then typing `hi` will show:  
```
Hello, Yamuna!
```

---

##  Useful Commands Summary

```bash
ls       # List files
cd ..    # Go back
mkdir    # Make folder
touch    # Make file
rm       # Delete file
mv       # Rename/move
cp       # Copy file
alias    # Create shortcut
source   # Reload .bashrc
```

---

Created by **Yamuna** – beginner but serious about learning Linux! 
