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

8. Which signal cannot be caught or ignored?

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

---

## Week 7 – Practice Questions  

### Multiple-Choice Questions (MCQ)

1. Which of the following describes the correct order of Bash expansions?
   A) Variable → Brace → Arithmetic → Command  
   B) Brace → Tilde → Parameter → Command → Arithmetic → Word Splitting → Filename  
   C) Filename → Word Splitting → Brace → Parameter  
   D) Arithmetic → Tilde → Brace → Parameter  

2. What does brace expansion do?
   A) Runs mathematical expressions  
   B) Expands variables into values  
   C) Generates lists or sequences  
   D) Performs pattern matching  

3. What does `~` expand to (unquoted)?
   A) The root directory  
   B) The user’s shell  
   C) The user’s home directory  
   D) `/tmp`  

4. What does `${#name}` return?
   A) The number of files in a directory  
   B) The length of the variable’s value  
   C) The exit status of the previous command  
   D) The number of arguments  

5. What does `${file##*.}` extract?
   A) The directory name  
   B) The filename without extension  
   C) Only the extension  
   D) The first character  

6. What does `$(command)` represent?
   A) Array expansion  
   B) Command substitution  
   C) Function declaration syntax  
   D) File descriptor redirection  

7. Which operator will expand unquoted words into multiple items based on whitespace?
   A) Word splitting  
   B) Parameter expansion  
   C) Regex expansion  
   D) Arithmetic evaluation  

8. What does the wildcard `?` match?
   A) Any number of characters  
   B) Digits only  
   C) Zero or one character  
   D) Exactly one single character  

9. Which syntax defines a Bash function?
   A) fun { ... }  
   B) function fun() { ... } or fun() { ... }  
   C) newfun = function { ... }  
   D) define fun { ... }  

10. What does `read -p "Name: " name` do?
    A) Reads a file  
    B) Prompts the user and stores input in `name`  
    C) Creates a new variable  
    D) Reads silently without echoing  


### Short-Answer Questions

1. List all seven types of expansion performed by Bash in order.

2. Provide an example of brace expansion that generates:  
   file1 file2 file3

3. What does tilde expansion do?

4. Write an example of command substitution that stores the current date in a variable `now`.

5. How do you extract the file extension from the variable `path`?

6. How do you loop through the items in the array `colors=("red" "blue" "green")`?

7. What does `${arr[@]}` return when `arr` is an array?

8. What does arithmetic expansion look like in Bash? Provide an example.

9. What does `read -s` do, and why is it useful?

10. Write a small Bash function named `greet` that prints:  
    Hello, NAME  
    using the first argument passed to it.

---

## Week 9 – Practice Questions  

### Multiple-Choice Questions (MCQ)

1. Which file contains user account information such as username, UID, GID, home directory, and login shell?
   A) /etc/shadow  
   B) /etc/passwd  
   C) /etc/group  
   D) /etc/login  

2. Which file stores encrypted password hashes and is readable only by root?
   A) /etc/passwd  
   B) /etc/shadow  
   C) /etc/auth  
   D) /etc/secure  

3. Which UID belongs to the root user?
   A) 1000  
   B) 65534  
   C) 0  
   D) 1  

4. Which command creates a new user with a login shell?
   A) useradd -s /bin/bash name  
   B) mkuser name  
   C) newuser --shell name  
   D) addaccount name  

5. Which command adds a user to an additional group without removing existing memberships?
   A) useradd group user  
   B) usermod -aG group user  
   C) addgroup user group  
   D) useredit group user  

6. What do the permission bits `rw-` translate to in octal?
   A) 2  
   B) 4  
   C) 6  
   D) 7  

7. What does the sticky bit do when set on a directory (e.g., /tmp)?
   A) Prevents anyone from writing inside it  
   B) Prevents users from deleting files they do not own  
   C) Forces all files to inherit owner permissions  
   D) Enables execution by all users  

8. What does the SUID bit do when applied to an executable?
   A) Runs the program as its file owner  
   B) Runs the program as the logged-in user  
   C) Shares execution privileges with the group  
   D) Makes the program unreadable  

9. Which command changes both the owner and the group of a file?
   A) chmod user:group file  
   B) chgrp user file  
   C) chown user:group file  
   D) own file user group  

10. Which command shows the groups a specific user belongs to?
    A) id user  
    B) groups user  
    C) group --list user  
    D) listgroups user  


### Short-Answer Questions

1. What are the three Linux permission classes?

2. What do the letters r, w, and x stand for?

3. Decode the permission string `drwxrw-r--` into user, group, and other permissions.

4. What information is stored in `/etc/passwd`?

5. What information is stored in `/etc/shadow`?

6. How do you set a password for a user named `mo`?

7. What UID range is typically used for normal (non-system) users?

8. What does the command `sudo userdel -r mo` do?

9. Write a command that sets file permissions to `644`.

10. Explain the difference between SUID and SGID in one sentence each.

---

## Week 10 – Practice Questions  

### Multiple-Choice Questions (MCQ)

1. What is systemd?
   A) A logging system only  
   B) A bootloader  
   C) The init system (PID 1) and service manager  
   D) A package manager  

2. Which command checks the status of a systemd service?
   A) sys status `<unit>`  
   B) systemctl check `<unit>`  
   C) service show `<unit>`  
   D) systemctl status `<unit>`  

3. Which command starts a systemd service?
   A) systemctl enable `<unit>`  
   B) systemctl start `<unit>`  
   C) run `<unit>`  
   D) service begin `<unit>`  

4. Where should administrator-created or custom unit files be placed?
   A) /usr/lib/systemd/system/  
   B) /etc/systemd/system/  
   C) /var/systemd/units/  
   D) ~/.config/systemd/units/  

5. What does the `ExecStart=` directive specify inside a `.service` file?
   A) Unit description  
   B) Dependencies  
   C) The command that the service runs  
   D) The target the service belongs to  

6. What does `systemctl daemon-reload` do?
   A) Reloads log files  
   B) Reloads all running services  
   C) Reloads unit file definitions  
   D) Reboots systemd  

7. Which of the following is the multi-user, non-GUI target?
   A) graphical.target  
   B) network.target  
   C) multi-user.target  
   D) basic.target  

8. Which command lists all configured timers?
   A) timersctl list  
   B) systemctl list-units --timers  
   C) systemctl list-timers  
   D) systemctl timers  

9. In a `.timer` unit, what does `OnCalendar=` define?
   A) Startup dependencies  
   B) The boot delay before starting  
   C) A calendar-based schedule  
   D) The timezone  

10. What does `systemctl enable --now myservice.service` do?
    A) Starts the service only  
    B) Enables the service on next boot only  
    C) Enables the service now and on boot  
    D) Stops the service if running  


### Short-Answer Questions

1. What is the purpose of a unit file in systemd?

2. What is PID 1, and why is it important?

3. Explain the difference between `systemctl start` and `systemctl enable`.

4. What does the `WantedBy=` directive do inside a unit file?

5. Write the command used to restart a service named `backup.service`.

6. What is a systemd “target”? Give an example.

7. What does the `OnBootSec=` timer directive specify?

8. How do you reload unit definitions after editing a service file?

9. What command shows all failed systemd units?

10. Name the directories for:  
    a) default packaged service files  
    b) custom admin-defined service files  

---

## Week 11 – Practice Questions  

### Multiple-Choice Questions (MCQ)

1. What service collects and manages logs on systemd-based systems?
   A) syslogd  
   B) journalctl  
   C) systemd-journald  
   D) logrotate  

2. Where are volatile journal logs stored?
   A) /var/log/journal  
   B) /run/log/journal  
   C) /etc/journal  
   D) /tmp/journal  

3. Where are persistent journal logs stored?
   A) /run/log/journal  
   B) /var/log/journal  
   C) /usr/lib/journal  
   D) /home/logs  

4. Which command shows all logs from the current boot?
   A) journalctl -a  
   B) journalctl -k  
   C) journalctl -b  
   D) journalctl --now  

5. Which command lists all previous boot sessions?
   A) journalctl --boot-list  
   B) journalctl list-boots  
   C) journalctl --list-boots  
   D) bootsctl list  

6. Which priority option shows only error-level logs?
   A) -p info  
   B) -p warning  
   C) -p err  
   D) -p critical  

7. Which command filters logs by systemd unit?
   A) journalctl service=`<unit>`  
   B) journalctl unit `<unit>`  
   C) journalctl -u `<unit>`  
   D) logs -u `<unit>`  

8. What does `journalctl -k` show?
   A) All system logs  
   B) Kernel-only messages  
   C) All logs from last hour  
   D) User messages  

9. Which output mode prints logs as formatted JSON?
   A) journalctl -o json  
   B) journalctl -o json-pretty  
   C) journalctl -o verbose  
   D) journalctl -o structured  

10. After modifying `/etc/systemd/journald.conf`, which command applies changes?
    A) journalctl restart  
    B) systemctl reload journald  
    C) systemctl restart systemd-journald  
    D) systemd --reload  


### Short-Answer Questions

1. What types of messages does systemd-journald collect?

2. What is the difference between volatile and persistent log storage?

3. What condition triggers journald to use persistent logs automatically?

4. How do you view kernel-only messages?

5. How do you view logs from the previous boot?

6. What does the `-p` option do in journalctl?

7. Write a command that shows all logs from the `ssh` service since today.

8. What does `journalctl -f` do?

9. Where is the main journald configuration file located?

10. After editing journald’s config, what command must be run to apply the changes?







