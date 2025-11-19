Perfect — here is your **Week 2 Practice Quiz**, based ONLY on Week 2 technical content (shell, commands, navigation, PATH, man pages, Git basics, Markdown) from your notes .

**No instructor-policy questions.  
No AI-policy questions.  
Pure Linux & Git commands.**

---

# 📝 **ACIT 2420 — Week 2 Practice Quiz**

## **Part A — Multiple Choice (12 questions)**

**1. What does the shell do?**  
A) Compiles C programs  
B) Interprets and executes commands  
C) Displays the GUI  
D) Manages the Linux kernel

---

**2. Which command shows your current shell?**  
A) `cat $SHELL`  
B) `which SHELL`  
C) `echo $SHELL`  
D) `shell --version`

---

**3. Which is _not_ a shell?**  
A) bash  
B) zsh  
C) fish  
D) wezterm

---

**4. What does `cd` do with no arguments?**  
A) Goes to `/`  
B) Goes to `/home`  
C) Goes to the previous directory  
D) Returns to your `$HOME` directory

---

**5. Which `ls` flag shows hidden files?**  
A) `-h`  
B) `-a`  
C) `-H`  
D) `-s`

---

**6. Which command creates nested directories if parents don’t exist?**  
A) `mkdir -H`  
B) `mkdir -r`  
C) `mkdir -p`  
D) `mkdir -n`

---

**7. What does the wildcard `*` do in a command like `rm *.txt`?**  
A) Deletes everything recursively  
B) Matches any characters before `.txt`  
C) Expands shell variables  
D) Shows hidden files

---

**8. Which command shows a manual page for a utility?**  
A) `help`  
B) `man`  
C) `info`  
D) `doc`

---

**9. What does `man -k user` do?**  
A) Shows user accounts  
B) Searches manpages for the keyword “user”  
C) Lists manuals owned by "user"  
D) Shows manpage sections about login

---

**10. What command initializes a Git repository?**  
A) `git start`  
B) `git create`  
C) `git init`  
D) `git repo`

---

**11. Which file contains global Git configuration?**  
A) `~/.git/config`  
B) `~/.git_global`  
C) `/etc/git.conf`  
D) `~/.config/git/config`

---

**12. What command stages files for commit in Git?**  
A) `git stage`  
B) `git push`  
C) `git add`  
D) `git prepare`

---

# **Part B — True or False (8 questions)**

**13. Linux filenames are case-sensitive.**  
True / False

---

**14. `cd ..` moves you one directory up.**  
True / False

---

**15. `rm` moves files to a trash/recycle bin.**  
True / False

---

**16. `help` is used for shell built-ins like `cd`.**  
True / False

---

**17. Git commits require you to add files to the staging area first.**  
True / False

---

**18. Markdown headings use `#` characters.**  
True / False

---

**19. `git init` should never be run inside your home directory.**  
True / False

---

**20. Running `git clone` automatically creates and initializes the new directory as a repo.**  
True / False

---

# **Part C — Short Answer (6 questions)**

**21. Explain the difference between a utility and a command.**  
_(Hint: Week 2 notes explicitly define it)_

---

**22. What does `$PATH` represent?**

---

**23. Give an example of a built-in shell command.**

---

**24. What does this command do?**

```
cp -r /etc/init.d .
```

---

**25. Write the command to search for the keyword “network” in manpage descriptions.**

---

**26. After modifying a file in your Git project, what are the two commands (in order) needed to save the change locally?**

---

# **Part D — Practical / Fill in the Blank (4 questions)**

**27. Fill in the missing command to create a repo and push to sourcehut:**

```
git init
git _____ README.md
git commit -m "initial commit"
git remote add origin git@git.sr.ht:~user/example
git _____ -u origin main
```

---

**28. Write a Markdown heading level 3 that says “Linux Commands”.**

---

**29. What command would you use to list files in long format, including hidden ones?**

---

**30. You want to create this directory structure in one command:**

```
projects/
    acit/
        week2/
```

Write the full `mkdir` command.

---

---

When you're ready, tell me:

👉 **“Here are my answers”**  
and I will **grade** them.