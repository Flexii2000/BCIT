

# 📝 **ACIT 2420 — Week 3 Practice Quiz**

# **Part A — Multiple Choice (12 questions)**

**1. Which directory contains configuration files?**  
A) `/var`  
B) `/etc`  
C) `/boot`  
D) `/opt`

---

**2. What does `/proc` contain?**  
A) Device files  
B) Kernel modules  
C) Pseudo-files for processes  
D) User home directories

---

**3. Which directory holds variable data files such as logs?**  
A) `/var`  
B) `/home`  
C) `/etc`  
D) `/srv`

---

**4. What command creates a symbolic link?**  
A) `ln`  
B) `ln -l`  
C) `ln -h`  
D) `ln -s`

---

**5. In an `ls -l` listing, how are symbolic links shown?**  
A) As regular files  
B) As `l` in the first column, with `->` pointing to the target  
C) As `s` in the first column  
D) As inode numbers

---

**6. Which Vim mode lets you type normally into the buffer?**  
A) Normal mode  
B) Insert mode  
C) Visual mode  
D) Command mode

---

**7. Which Vim key enters Insert mode _at the cursor_?**  
A) `i`  
B) `a`  
C) `Shift+a`  
D) `:`

---

**8. Which Vim motion moves the cursor to the first line of the file?**  
A) `0`  
B) `gg`  
C) `$`  
D) `G`

---

**9. Which `find` command finds all `.txt` files in the current directory and subdirectories?**  
A) `find . *.txt`  
B) `find -type f -name "*.txt"`  
C) `find . -type f -name "*.txt"`  
D) `find . -r *.txt`

---

**10. What does this do?**  
`find . -type f -mmin -10`  
A) Finds files modified over 10 MB in size  
B) Finds files modified more than 10 days ago  
C) Finds files modified less than 10 minutes ago  
D) Finds files modified between 10 and 20 minutes ago

---

**11. Which `grep` option searches recursively?**  
A) `-i`  
B) `-r`  
C) `-c`  
D) `-C`

---

**12. Which grep command prints two lines above and below matches?**  
A) `grep -c`  
B) `grep -iw`  
C) `grep -C 2`  
D) `grep -r`

---

# **Part B — True or False (8 questions)**

**13. `/boot` contains files used before the kernel starts user-mode programs.**  
True / False

---

**14. A symbolic link contains a pointer to the target file’s inode.**  
True / False

---

**15. You can create a hard link to a directory.**  
True / False

---

**16. Vim’s Normal mode is the mode you spend most of your time in.**  
True / False

---

**17. `:%d` in Vim deletes the entire file.**  
True / False

---

**18. `grep -iw` ignores case and matches whole words.**  
True / False

---

**19. `/dev` contains device files.**  
True / False

---

**20. `find . -type f -mtime +10` finds files whose contents were modified more than 10 days ago.**  
True / False  
(Hint: mtime = contents)

---

# **Part C — Short Answer (6 questions)**

**21. What does a pseudo-filesystem allow you to do?**  
(One sentence only.)

---

**22. Write the command to make a symlink named `loglink` pointing to `/var/log`.**

---

**23. In Vim, what does `dd` do?**

---

**24. What is the difference between `ci"` and `ca"` in Vim?**  
(Short explanation.)

---

**25. Write a `find` command to list files larger than 5 MB in `/home`.**

---

**26. What does this command do?**  
`grep -rl "docker" /etc`

---

# **Part D — Practical / Fill in the Blank (4 questions)**

**27. Fill in the blank:**  
To open a file named `config.txt` in Vim:  
`vim ________`

---

**28. Fill in the blank:**  
In Vim, to save and quit in one command:  
`________`

---

**29. Fill in the blank:**  
To search inside Vim for the word "error":  
`/________`

---

**30. Write a grep command that counts occurrences of the word "set" in `~/.bashrc`.**

---

---

When you're ready, send me your **answers**, and I'll grade them.