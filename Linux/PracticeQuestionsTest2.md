## SSH – Practice Questions

### Multiple-Choice Questions (MCQ)

1. Which command creates a new SSH key pair?
   A) ssh-newkey  
   B) ssh-add  
   C) ssh-keygen  
   D) keygen-ssh  

2. Where are a user’s SSH public and private keys normally stored (default names)?
   A) /etc/ssh/keys/  
   B) ~/.ssh/key and ~/.ssh/key.pub  
   C) /usr/ssh/keys/  
   D) ~/.keys/  

3. What is the purpose of `~/.ssh/known_hosts`?
   A) Store usernames and passwords  
   B) Store fingerprints of SSH servers you have connected to  
   C) Store your local SSH keypairs  
   D) Store SSH logs  

4. Which file allows you to define SSH host aliases like `Host myserver` so you can type `ssh myserver`?
   A) ~/.ssh/alias  
   B) ~/.ssh/config  
   C) /etc/ssh/config  
   D) /etc/ssh/ssh.conf  

5. Which ssh-keygen option lets you specify the filename/path of the keypair?
   A) -p  
   B) -f  
   C) -a  
   D) -r  

6. Which ssh-keygen option adds a comment (for example, an email address) to a key?
   A) -c  
   B) -C  
   C) -m  
   D) -A  

7. In an SSH config entry, what does the `IdentityFile` option specify?
   A) The username used for login  
   B) The host’s fingerprint  
   C) The path to the private key to use  
   D) The port number for SSH  

8. What does the line `PreferredAuthentications publickey` in `~/.ssh/config` do?
   A) Disables SSH logins  
   B) Forces password authentication  
   C) Prefers key-based authentication over other methods  
   D) Selects which host key algorithm to use  

9. What is the effect of setting `StrictHostKeyChecking no` in your SSH config?
   A) SSH will refuse all new host keys  
   B) SSH will automatically accept new host keys without asking  
   C) SSH will delete existing host keys  
   D) SSH will only allow root logins  

10. Which of the following is a valid way to start an SSH connection using either your config or direct connection syntax?
    A) ssh connect username ip  
    B) ssh username:ip  
    C) ssh hostname  
    D) ssh --user username --host ip  


### Short-Answer Questions

1. Which command do you run to generate a new SSH key pair with default settings?

2. What is stored in the file `~/.ssh/known_hosts`, and why is it important?

3. Where is the user-specific SSH configuration file located that allows you to define `Host` aliases?

4. In an SSH config entry, what does `HostName` specify?

5. In an SSH config entry, what does `User` specify?

6. What is the purpose of the `IdentityFile` option in `~/.ssh/config`?

7. Give an example of how you would start an SSH connection using a configured host alias from `~/.ssh/config`.

8. Which ssh-keygen option would you use to specify a non-default filename for your new key pair?

9. Why is key-based authentication generally preferred over password authentication for SSH?

10. Explain briefly what happens the first time you connect to a new SSH server (with default settings) in terms of host keys and confirmation.

---

## Cloud-Init – Practice Questions


### Multiple-Choice Questions (MCQ)

1. What must every cloud-init configuration file begin with?
   A) \#init  
   B) \#cloud-start  
   C) \#cloud-config  
   D) \#first-boot  

2. What is the main purpose of cloud-init?
   A) Manage long-running system services  
   B) Automate VM initialization on the first boot  
   C) Configure network routing tables  
   D) Provide shell access for debugging  

3. Where does cloud-init store its internal state and metadata?
   A) /etc/cloud/instances  
   B) /var/cloud/  
   C) /var/lib/cloud/  
   D) /usr/local/cloud/  

4. Where are cloud-init logs stored?
   A) /var/log/init.log  
   B) /var/log/cloud-init.log  
   C) /tmp/cloud.log  
   D) /root/cloud-init-output.log  

5. Which command checks the current cloud-init status?
   A) cloud-init check  
   B) cloud-init status  
   C) systemctl cloud-init  
   D) initctl status cloud  

6. Which section in cloud-config is used to create Linux users before the first login?
   A) account:  
   B) add-user:  
   C) users:  
   D) newusers:  

7. What does the `ssh-authorized-keys:` section do?
   A) Generates new SSH keys for the VM  
   B) Imports public keys that can SSH into the VM  
   C) Edits sshd_config dynamically  
   D) Removes unused SSH keys  

8. Which section installs software packages during the VM’s initial boot?
   A) install:  
   B) pkg-install:  
   C) packages:  
   D) setup:  

9. What does the setting `disable_root: true` accomplish?
   A) Deletes the root account  
   B) Disables the root filesystem  
   C) Disables SSH login for the root user  
   D) Disables password authentication  

10. Where are additional cloud-init configuration fragments stored?
    A) /etc/cloud.d/  
    B) /etc/cloud/cloud.cfg.d/  
    C) /usr/lib/cloud.d/  
    D) /var/lib/cloud/config/  


### Short-Answer Questions

1. What is cloud-init, and what problem does it solve when deploying new virtual machines?

2. What line must always appear at the top of any cloud-config file?

3. Where does cloud-init write its detailed execution logs?

4. What is the purpose of the `users:` section in a cloud-config file?

5. What does the `ssh-authorized-keys:` list control?

6. Where does cloud-init store internal state and processed configuration data?

7. How do you check whether cloud-init has finished running on a new VM?

8. What does the `packages:` section do in a cloud-init file?

9. Why does DigitalOcean allow you to paste your cloud-config into the “User Data” field when creating a Droplet?

10. After the VM is created using cloud-init, which command allows you to manually set a password for a newly created user?

---

## Vim Essentials – Practice Questions


### Multiple-Choice Questions (MCQ)

1. Which mode is Vim in by default when you open a file?
   A) Insert mode  
   B) Visual mode  
   C) Normal mode  
   D) Command-line mode  

2. Which key is used to enter Insert mode?
   A) a  
   B) i  
   C) v  
   D) :  

3. Which key returns Vim to Normal mode?
   A) ESC  
   B) CTRL  
   C) TAB  
   D) SHIFT  

4. What does the command `dd` do?
   A) Delete a word  
   B) Delete a character  
   C) Delete the entire line  
   D) Delete from cursor to end of line  

5. Which command copies (yanks) the current line?
   A) cc  
   B) yy  
   C) dd  
   D) yw  

6. Which command pastes text *after* the cursor?
   A) P  
   B) p  
   C) y  
   D) :paste  

7. What does `/word` do in Vim?
   A) Replace the word  
   B) Search forward for the word  
   C) Search backward for the word  
   D) Delete the word  

8. What does `:wq` do?
   A) Quit without saving  
   B) Save only  
   C) Save and quit  
   D) Force quit  

9. What is the command to go to the top of a file?
   A) G  
   B) gg  
   C) 0  
   D) ^  

10. Which of the following switches to Visual mode?
    A) V  
    B) i  
    C) v  
    D) :v  


### Short-Answer Questions

1. Name the three main Vim modes described in the course notes.

2. How do you enter Insert mode from Normal mode?

3. How do you return to Normal mode from any other mode?

4. What does the command `x` do?

5. What is the difference between `p` and `P` when pasting?

6. How do you search backward in Vim?

7. What does the command `:%s/old/new/g` accomplish?

8. What does `yw` do?

9. Which command takes you to the bottom of the file?

10. How do you open a new file from within Vim?

---

## Week 1 & Week 2 – Practice Questions  


### Multiple-Choice Questions (MCQ)

1. Linux filesystems are:
   A) Case-insensitive  
   B) Case-sensitive  
   C) Sometimes case-sensitive  
   D) Case-random  

2. Which of the following are three different files on Linux?
   A) file, FILE, File  
   B) file1, file1, file1  
   C) file.txt, file.TXT, file.txt.bak  
   D) None of the above  

3. Which command prints the value of an environment variable?
   A) print VAR  
   B) echo VAR  
   C) echo $VAR  
   D) var echo VAR  

4. Which symbol in the shell prompt indicates a **normal** user?
   A) %  
   B) $  
   C) #  
   D) @  

5. Which directory contains a user’s personal shell configuration?
   A) /etc/  
   B) /bin/  
   C) /usr/local/  
   D) ~/  

6. What does the command `cd` without arguments do?
   A) Prints current directory  
   B) Goes to /root  
   C) Goes to the user’s home directory  
   D) Clears the screen  

7. Which command lists all files, including hidden ones?
   A) ls  
   B) ls -a  
   C) ls -h  
   D) ls --all-hidden-only  

8. What is the purpose of the PATH variable?
   A) Stores your current directory  
   B) Tells the shell where to look for commands  
   C) Lists all environment variables  
   D) Sets the default user  

9. What does the wildcard `*` match?
   A) One character  
   B) Digits only  
   C) Any number of characters  
   D) Uppercase characters only  

10. Which command shows a manual page for a utility?
    A) help utility  
    B) man utility  
    C) utility --man  
    D) manual utility  


### Short-Answer Questions

1. Why are file names like `Ocean`, `ocean`, and `OCEAN` considered different in Linux?

2. What command shows which shell you are currently using?

3. Explain what the shell does in one sentence.

4. What does the `$PATH` environment variable contain?

5. How do you list hidden files in a directory?

6. What does the prompt symbol `#` indicate?

7. Give an example of using a wildcard to remove all `.log` files.

8. What command shows a list of directories contained in your PATH?

9. What is the difference between running a command like `ls` and running a script using `./scriptname`?

10. What is the difference between a command, a utility, and a program according to the notes?

---

## Week 3 – Practice Questions  


### Multiple-Choice Questions (MCQ)

1. A symbolic link (symlink) is:
   A) A duplicate copy of a file  
   B) A file that stores a pointer to another file’s path  
   C) A compressed file  
   D) A temporary cache file  

2. Which command creates a symbolic link?
   A) link  
   B) cp -s  
   C) ln -s  
   D) symlink-create  

3. Which command shows the target of a symlink?
   A) ls  
   B) ls -l  
   C) cat  
   D) file  

4. In `lrwxrwxrwx 1 root root 9 Jan 12 15:29 yes -> coreutils*`, the arrow (`->`) indicates:
   A) File permissions  
   B) File owner  
   C) The destination of the symbolic link  
   D) A corrupted file  

5. The command `find . -type f -name "*.txt"` does what?
   A) Finds all empty files  
   B) Finds all files ending with `.txt`  
   C) Replaces all .txt files  
   D) Finds only files in /tmp  

6. What does the `-exec` option in `find` do?
   A) Executes a command on each matched file  
   B) Sorts the output  
   C) Compresses found files  
   D) Prompts for confirmation  

7. Which command searches for text inside files?
   A) find  
   B) search  
   C) grep  
   D) match  

8. What does `grep -r pattern directory/` do?
   A) Searches only the current file  
   B) Searches recursively through a directory  
   C) Replaces a pattern  
   D) Prints only filenames  

9. What does the pipe operator `|` do?
   A) Splits a file  
   B) Sends the output of one command into another  
   C) Redirects output to a file  
   D) Moves files between directories  

10. Which command prints filenames that contain a match?
    A) grep -C  
    B) grep -w  
    C) grep -l  
    D) grep -n  


### Short-Answer Questions

1. What is a symbolic link and why is it useful?

2. Write the command to create a symlink named `python` pointing to `/usr/bin/python3`.

3. How can you view a symlink’s target?

4. What is the difference between `mtime` and `ctime` in the `find` command?

5. Write a `find` command that lists all files larger than 10 MB.

6. What does `grep -i` do?

7. Write a command that searches for the word “error” in all `.log` files in the current directory.

8. What does the command `grep -C 2 "warning" logfile` show?

9. Explain what the pipe symbol (`|`) does in command-line workflows.

10. What is the difference between `grep pattern file` and `find . -name pattern`?

---

## Week 4 – Practice Questions  

### Multiple-Choice Questions (MCQ)

1. What is a process in Linux?
   A) A directory  
   B) A running instance of a program  
   C) A configuration file  
   D) A driver  

2. Which directory contains runtime information for all processes?
   A) /etc/proc  
   B) /proc  
   C) /run  
   D) /sys  

3. Which PID is always associated with the init system (systemd) on Debian?
   A) 0  
   B) 1  
   C) 42  
   D) 999  

4. Which command prints the exit code of the last executed command?
   A) echo $?  
   B) exit $?  
   C) show-exit  
   D) status-last  

5. What is the exit code for a successful command?
   A) 1  
   B) 0  
   C) 2  
   D) 255  

6. Which keyboard shortcut searches through previous shell history?
   A) Ctrl+s  
   B) Ctrl+r  
   C) Ctrl+h  
   D) Ctrl+p  

7. Which signal is sent by pressing Ctrl+C?
   A) SIGSTOP  
   B) SIGTERM  
   C) SIGKILL  
   D) SIGINT  

8. Which signal **cannot** be caught or ignored?
   A) SIGTERM  
   B) SIGSTOP  
   C) SIGKILL  
   D) SIGUSR1  

9. Which command lists all running processes?
   A) ps -a  
   B) ps -e  
   C) ps -k  
   D) ps --all-users-only  

10. What does `kill -9 PID` do?
    A) Gracefully stop a process  
    B) Pause a process  
    C) Forcefully kill a process immediately  
    D) Restart a process  


### Short-Answer Questions

1. What does the directory `/proc` contain, and why is it described as a “pseudo-filesystem”?

2. What is special about PID 1?

3. How do you check the exit code of the most recently run command?

4. Explain the purpose of the `SIGTERM` signal.

5. What is the difference between `SIGTERM` and `SIGKILL`?

6. Write a command that lists all running processes in a full, detailed format.

7. Write a command that kills every process with the name “firefox” using a pattern match.

8. How do you search your command history interactively?

9. What does `ps -eo comm,pid,%cpu` show?

10. What does the `--forest` option do when running `ps`?

---

## Week 5 – Practice Questions  

### Multiple-Choice Questions (MCQ)

1. What is the purpose of the **shebang** (`#!`) at the top of a script?
   A) Sets file permissions  
   B) Specifies which interpreter should run the script  
   C) Creates environment variables  
   D) Marks comments for the shell  

2. What command makes a script executable?
   A) chmod u-r script.sh  
   B) chmod +exec script.sh  
   C) chmod u+x script.sh  
   D) script --executable  

3. Which type of quotes **do not** allow variable expansion?
   A) "double quotes"  
   B) 'single quotes'  
   C) `backticks`  
   D) `<<EOF`  

4. Which special variable contains the script’s own filename?
   A) $1  
   B) $0  
   C) $?  
   D) $@  

5. Which Bash test syntax is considered safer and more feature-complete?
   A) `[ ]`  
   B) test  
   C) (( ))  
   D) `[[ ]]`  

6. What does the command `source ~/.bashrc` do?
   A) Reloads the system PATH permanently  
   B) Reloads shell configuration without starting a new shell  
   C) Deletes the .bashrc file  
   D) Runs .bashrc in a subshell  

7. What does the `alias` command do?
   A) Creates a new file  
   B) Creates a shortcut for a command  
   C) Defines a new environment variable  
   D) Adds a script to PATH  

8. Which file is executed for **login shells**?
   A) ~/.bashrc  
   B) ~/.bash_profile  
   C) ~/.bash_history  
   D) /etc/profile.d/login.sh  

9. Which file is executed for non-login interactive shells?
   A) ~/.bash_profile  
   B) ~/.bashrc  
   C) /usr/bin/bash  
   D) ~/.profile  

10. What does command substitution do?
    A) Runs a command in the background  
    B) Inserts the output of one command into another  
    C) Converts commands into text  
    D) Prints command history  


### Short-Answer Questions

1. What is the purpose of the shebang (`#!`) at the top of a script file?

2. How do you make a Bash script named `run.sh` executable?

3. Explain the difference between double quotes and single quotes in Bash.

4. What does `$?` represent?

5. What does `$1` represent inside a Bash script?

6. What does the command `export VAR=value` do?

7. Which file should you edit to add aliases that load for every interactive shell session?

8. Write an example of a simple Bash alias named `ll` that runs `ls -alh`.

9. What does the `local` keyword do inside a Bash function?

10. What is the purpose of command substitution, and give one example of its use.


