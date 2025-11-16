€## Test 2 preparation

#### Content Overview
- cumulative tests
- all topics starting at week 1 until week 11 can and will be part of the test
- week 1-11 notes summarized

#### SSH
1. Important files and their locations
- `~/.ssh/config` config file for general ssh settings
- `~/.ssh/known_hosts` security file with a list of servers I've connected to in the past (fingerprints)
- `~/.ssh/key.pub` and `~/.ssh/key` ssh public and private key pair for a safe ssh connection

2. The ssh config file
The config file establishes ssh connection dependencies for every used ssh connection. The following is a draft of an entry in this file
```bash
Host hostname
  HostName ip_addres
  User username
  PreferredAuthentications publickey
  IdentityFile ~/.ssh/identityFile
  Port somePortNumber
  StrictHostKeyChecking no
  UserKnownHostsFile /dev/null
```
- with `ssh hostname` we can start a connection without using `ssh username@ip_address`. Both ways work but the first one is generally more convenient.

3. ssh commands
- `ssh hostname` or `ssh username@ip_address` start the desired ssh connection
- `ssh-keygen` create a new ssh key pair. To specify a path we use `ssh-keygen -f ~/.ssh/someKey` (creates someKey and someKey.pub)
- `ssh-keygen -t ed25519 -C "you@example.com"` adds a ssh type (`-t`) and a comment to the new key pair (`-C`)

---

#### Cloud-Init  
1. Important files and their purpose  
- `cloud-config.yaml` main configuration file used to automate server setup on the first boot  
- `/var/log/cloud-init.log` detailed log output for debugging cloud-init execution  
- `/var/lib/cloud/` directory where cloud-init stores internal state, instance metadata, and processed configs  
- `/etc/cloud/cloud.cfg.d/` directory containing additional cloud-init configuration fragments  

2. The cloud-config.yaml file  
The cloud-config file defines everything that should happen the first time a VM boots.  
It uses YAML syntax and always starts with:

    #cloud-config

A minimal example for creating a user, adding an SSH key, and installing a package:

    #cloud-config
    users:
      - name: username
        primary_group: username
        groups: sudo
        shell: /bin/bash
        sudo: "ALL=(ALL) NOPASSWD:ALL"
        ssh-authorized-keys:
          - ssh-ed25519 AAAA...yourPublicKey...

    packages:
      - tmux

    disable_root: true

- `users:` creates a new Linux user before first login  
- `ssh-authorized-keys:` adds your public key to `~/.ssh/authorized_keys`  
- `packages:` installs software packages during initialization  
- `disable_root:` disables SSH login for the root account  

3. cloud-init usage in practice  
- Paste your `cloud-config.yaml` into DigitalOcean’s “Add Initialization Scripts (user data)” field when creating a Droplet  
- DigitalOcean passes this file to the VM, and cloud-init runs it exactly once during first boot  
- After VM creation, connect using SSH and set your user password:  
      sudo passwd username  
- To verify cloud-init execution, use:  
      sudo cloud-init status  
      sudo cat /var/log/cloud-init.log

---

#### Vim essentials
1. Different vim modes
> - `Normal` Vim's standard mode which is used whenever vim is started by a user. Enter by pressing `ESC`
> - `Insert` Vim's text input mode, accessed by using `i`, to return to normal you press `ESC`
> - `Visual` Vim's mode for selecting text. Entered by using `v`, to return to normal you press `ESC`

2. Basic vim commands in `Normal` mode
Moving around in vim
- `h` going one character **left**
- `j` going one character **down**
- `k` going one character **up**
- `l` going one character **right**

- `w` going to the next word. A word in vim is every block of letters, numbers and underscores with **no blanks**!
- `W` going to the next word which follows a blank. Usually the intended way of jumping to the next word.
- `b` going to the previous word following the `w` definition
- `B` going to the previous word following the `W` definition
- `gg` moving up to the top of the vim file
- `G` moving down to the bottom line of the vim file
- `0` moving to the start of a line
- `$` moving to the end of a line

Editing a file
- `x` deleting the next character under cursor
- `dd` delete current line
- `dw` delete the current word
- `yy` copy line (yy comes from yanking the line)
- `yw` copy word
- `p` paste copied content after cursor
- `P` paste copied content before cursor
- `u` undo changes (revert)
- `CTRL + r` redo changes

Search and Replace
- `/word` search for the pattern `word` in the entire document
- `?word` search for `word` backwards
- `:%s/old/new/g` Replace all `old` with the word `new`
- `:s/old/new/g` Replace `old` with the word `new` in the current line

3. Basic vim commands in `Command line` mode
- `:` entering command line mode
- `:w` write out
- `:q` quit vim 
- `q!` quit vim forcefully
- `:wq` write out and quit vim (alternative: `:x`)
- `:e filename` open a new file in vim when you are already in vim 

#### Linux file hierarchy system (FHS)
```bash
/
├── bin/        → Essential user binaries (ls, cp, mv, cat and more)
├── sbin/       → System binaries (mount, shutdown)
├── etc/        → System-wide configuration files
├── home/       → User home directories
├── root/       → Home directory of root user
├── var/        → Variable data (logs, mail, cache)
├── tmp/        → Temporary files
├── usr/        → User programs, libraries, docs
├── lib/, lib64/ → Essential shared libraries
├── dev/        → Device files (e.g. disks, terminals)
├── proc/       → Kernel & process information (virtual)
├── sys/        → Kernel devices and system info (virtual)
├── boot/       → Bootloader files, kernel images
├── media/, mnt/ → Mount points for removable or temporary filesystems
```

#### Most relevant files and their paths
Global cnfiguration files
- `/etc/passwd` user account info (username, UID, shell, etc.)
- `/etc/shadow` encrypted password information
- `/etc/group` group definitions
- `/etc/sudoers` shows who can use sudo
- `/etc/resolv.conf` DNS resolver config

User files
- `~/.bashrc` user-specific shell config and aliases (sourced at every terminal start-up)
- `~/.bash_profile` commands that are run at login
- `~/.ssh/config` ssh config file to use the secure shell protocol
- `~/.vimrc` vim editor configuration
- `~/.gitconfig` git user and alias settings

System & Service management
- `/etc/systemd/system` custom systemd definitions like services or timers
- `/usr/lib/systemd/system` default systemd definitions
- `/var/log` general log files
- `/var/log/journal` persistent log files (not deleted at shutdown or before new boot)
- `/run/log/journal` temporary log files (deleted at shutdown or before new boot)
- `/var/log/dmesg` specific kernel log files (accessed with `journalctl -k`)

---

#### Week 1

Nothing major to summarize

---

#### Week 2

##### 1. Case Sensitivity in Linux  
Linux filesystems are case sensitive.  
This means `Ocean`, `ocean`, and `OCEAN` are three different files.  
Always pay attention to case when typing filenames, commands, or paths.

---

##### 2. What is the Shell?  
The shell is a program that lets you run commands on a computer.  
It allows full control of the system in a text-based environment.

- You can run programs (e.g., `ls`, `firefox`, `cat`)  
- You can navigate directories  
- You can write shell scripts to automate tasks  
- Many shell options exist; the most common ones:

###### Common Shells
- **Bash** – Default on most Linux distros (used in this course)  
- **Fish** – User-friendly, auto-completion, syntax highlighting  
- **zsh** – Default on macOS; common in Linux too  

Check which shell you're using:

    echo $SHELL

This prints the value of the SHELL environment variable.  
Environment variables use `$` when referenced.

---

##### 3. Running Commands in the Shell  
You start with a prompt similar to:

    user@host:~$

`$` means normal user, `#` means root user.

To run a command:
1. Type the command  
2. Press Enter  
3. The shell searches for the command in:
   - shell functions  
   - shell built-ins  
   - directories listed in `$PATH`  

Check your PATH:

    echo $PATH

If the command is found and executable, the shell runs it in a new process.

---

##### 4. Terminology  
- **Utility**: a small command-line program (e.g., `cat`)  
- **Command**: may contain multiple utilities, flags, pipes, etc.  
  Example:

    ps -eo comm,rss | grep bash

Contains:
- `ps`  
- `grep`  
- `|` (pipe)  
- arguments  

---

##### 5. Important Shell Commands

###### `cd` – change directory  
    cd Documents/scripts  
    cd ..            # go up one directory  
    cd               # go to home directory  

###### `ls` – list files  
    ls  
    ls -a            # show hidden files  
    ls -al           # long listing  

###### `mkdir` – make directories  
    mkdir newdir  
    mkdir -p one/two/three  

###### `cp` – copy  
    cp fileA fileB  
    cp -r dirA dirB   # recursive copy  

###### `rm` – remove  
`rm` does not use a trash bin.  
    rm file.txt  
    rm -rf dir/  
`-r` = recursive  
`-f` = force  

###### Wildcards  
    rm *.txt          # remove all .txt files  

---

##### 6. Getting Help

###### Manual pages for utilities:
    man ls  
    man mkdir  

###### Help for shell built-ins:
    help test  
    help cd  

###### Search man pages:
    man -k keyword  
Example:

    man -k user | grep create

`|` pipes the output of one command to another.

---

##### 7. Git Review

###### What is Git?  
Git is a Distributed Version Control System, used to track changes and collaborate on projects.

###### Installing Git  
Linux (Debian/Ubuntu):

    sudo apt install git


###### Git Configuration  
Git stores settings in:

- **Global**: `~/.gitconfig`  
- **Local (per repo)**: `.git/config`

Set your info:

    git config --global user.name "Your Name"
    git config --global user.email your@example.com
    git config --global init.defaultBranch main

View your config:

    git config --list --show-origin

Minimal example:

    [user]
        name = Your Name
        email = your@example.com
    [core]
        editor = vim
        autocrlf = false
    [init]
        defaultBranch = main

---

##### 8. Essential Git Commands

###### Initialize a repo
    git init

###### Add files to staging
    git add file1 file2  
    git add .             # add everything

##### Commit changes
    git commit -m "your message"

###### Push to remote  
Requires adding a remote first:

    git remote add origin git@git.sr.ht:~username/project
    git push -u origin main

---

##### 9. Git Workflow Summary

1. Create project directory  
2. Initialize:

       git init

3. Add/edit files  
4. Stage files:

       git add

5. Commit:

       git commit

6. Push to remote repo:

       git push

---

###### 10. Working With SourceHut (sr.ht)  
Example project setup:

    mkdir example
    cd example
    git init
    echo "Hello world" > README.md
    git add README.md
    git commit -m "Initial commit"
    git remote add origin git@git.sr.ht:~username/example
    git push -u origin main

###### When cloning a repo:

    git clone git@git.sr.ht:~username/example
    cd example
    echo "Hello world" > README.md
    git add README.md
    git commit -m "add README.md"
    git push

###### SSH config for Sourcehut (`~/.ssh/config`)

    Host *sr.ht
      IdentityFile ~/.ssh/hut
      PreferredAuthentications publickey

Add SourceHut host keys to `~/.ssh/known_hosts` as provided.

---

##### 11. Markdown Basics

###### Headings  
    # h1  
    ## h2  
    ### h3  

###### Links  
    [text](https://example.com)

###### Images  
    ![description](./path/to/image.jpg)

Use relative paths in Git repositories.

##### Code Blocks  
Three backticks before and after:

    ```bash
    echo "Hello world"
    ```

Markdown is plain text and easy to use, making it ideal for documentation.

---

#### Week 3

##### 1. Symbolic Links (Symlinks)

A symbolic link (or “symlink”) is a pointer to another file’s path.

###### Advantages  
- Can link to *directories*  
- Flexible and easy to update  
- Safer than hard links when linking across filesystems

###### Create a symbolic link  
    ln -s source_file symbolic_link

Example:  
    ln -s /usr/bin/python3 python

###### Viewing symlinks with `ls`  
    ls -l

Output example:  
    lrwxrwxrwx 1 root root   9 Jan 12 15:29 yes -> coreutils*

The arrow (`->`) shows the link target.

---

##### 2. Finding Files with find

The `find` utility searches based on **file properties** such as name, size, or modified time.

###### Basic syntax  
    find [options] [path...] [expression]

###### Examples  
- Find all regular files in home directory:  
      find ~ -type f

- Find all `.txt` files recursively:  
      find . -type f -name "*.txt"

- Find files modified in the last 10 minutes:  
      find . -type f -mmin -10

- Find files larger than 10 MB:  
      find / -size +10M

###### mtime vs ctime  
- `-mtime` → change in **content**  
- `-ctime` → change in **metadata** (permissions, owner, etc.)

###### Running a command with `-exec`  
    find . -type f -name "*.log" -exec rm {} \;

- `{}` = matched file  
- `\;` = run command once per file  
- `+` = batch files together for fewer commands

---

##### 3. Searching Text With **grep**

`grep` finds patterns of text in files.

###### Basic syntax  
    grep [OPTIONS] PATTERN [FILE...]

###### Examples
- Simple search:  
      grep word file.txt

- Ignore case + match whole words only:  
      grep -iw word file.txt

- Recursive search through directories:  
      grep -r pattern directory/

- Show 2 lines above and below match:  
      grep -C 2 "error" logfile

- Count occurrences:  
      grep -c "set" ~/.bashrc

- List only filenames that contain the pattern:  
      grep -rl "TODO" .

- Pipe example:  
      fc-list | grep -i "nerd"

`|` pipes output from one command into another.

---

##### 4. Regular Expressions (Regex)

`grep` supports regex for pattern matching.

Examples:

- Find any 2-digit number:  
      grep "[0-9]{2}" file

- Phone number formats:  
      grep -E '\(\d{3}\) \d{3}-\d{4}|\d{3}-\d{3}-\d{4}' file

Notes:
- `|` means OR **in regex**, not a pipe  
- Some systems require `grep -E` or `grep -P` for advanced patterns  

---

##### 5. Pipelines and Advanced Command Combinations

The **pipe** (`|`) sends output from one program into the next.

Examples:
- Search only in results of the first command:  
      man -k user | grep create

- Count occurrences from piped input:  
      journalctl -b | grep -c "warning"

Pipes make Linux extremely powerful by chaining commands.

---

#### Week 4

##### 1. Linux Processes  
A **process** is any running instance of a program (an executable file stored on disk).

- When you run a program, you create a process  
- Each process has a unique **PID** (Process ID)

###### The `/proc` Directory  
`/proc` is a **pseudo-filesystem** containing runtime system and process information.

Example: show the command for PID 1

    cat /proc/1/comm

Every running process has a directory inside `/proc` named after its PID.

###### PID 1 is special  
- PID 1 is always the **init system**  
- On Debian: PID 1 = `systemd`  
- PID 1 starts the entire user-space environment

---

##### 2. Exit Codes (Exit Status)

When a process finishes, it returns an **exit code**.

Check exit code of last command:

    echo $?

- `0` → success  
- non-zero → error or failure  

Try it:

    ls
    echo $?

→ should be `0`

    sweatyklingons
    echo $?

→ will be `127` (command not found)

---

##### 3. Shell History  
- Use **up / down arrow keys** to browse previous commands  
- Use **Ctrl+r** to search history interactively  
  (Type a few characters to filter past commands)

---

##### 4. Signals  
Signals allow users or processes to communicate with other running processes.

Common signals:

| Signal | Number | Meaning |
|--------|--------|---------|
| **SIGINT** | 2 | Interrupt (Ctrl + C) |
| **SIGKILL** | 9 | Force kill immediately |
| **SIGTERM** | 15 | Graceful shutdown |

List all signals:

    kill -l

###### Signal meanings  
- **SIGINT** → interrupt a foreground process  
- **SIGTERM** → request shutdown (preferred)  
- **SIGKILL** → force shutdown immediately (no cleanup)

---

##### 5. Discovering Processes with `ps`

Basic usage:

    ps

Example output:

    PID   TTY   TIME   CMD
    97350 pts/0 00:00:00 bash
    109522 pts/0 00:00:00 ps

See all processes:

    ps -e

View with a pager:

    ps -e | less

Search within the pager using `/bash`  
Exit pager with `q`

Use `grep` to filter:

    ps -e | grep -i bash

Format the output with `-o`:

    ps -eo comm,pid,%cpu | grep -i systemd

Show process hierarchy:

    ps -e --forest
or
    ps -H

---

##### 6. Terminating Processes with `kill` and `pkill`

###### kill  
Uses **PIDs**:

    kill [PID]
    kill -9 [PID]     # force kill

Example with command substitution:

    kill -9 $(pidof firefox)

###### pkill  
Uses **patterns**, easier to work with:

    pkill pattern
    pkill -9 pattern        # force kill
    pkill -15 pattern       # send SIGTERM
    pkill -u username proc  # kill process owned by a user

Be specific when multiple process names match.

---

##### 7. Shell Configuration Files

There are two shell types:

- **Login shell** → run at login  
- **Non-login shell** → when opening a new terminal or SSH session

###### Login configuration  
Files executed when logging in:

- `~/.bash_profile`  
- `~/.profile` (fallback if `.bash_profile` missing)

Good place for **environment variables**.

Example `~/.bash_profile`:

    # Source .bashrc if interactive
    if [[ $- == *i* && -f $HOME/.bashrc ]]; then
        source $HOME/.bashrc
    fi

    export EDITOR="vim"

###### Non-login configuration  
Executed for every new Bash instance:

- `~/.bashrc`

Good place for:

- prompt configuration  
- aliases  
- shell functions  

Example `~/.bashrc` (shortened):

    alias grep='grep --color=auto'
    alias ls="ls -alh"

    # Prompt
    PS1="\n\w@\h\n$ "

    # Example function
    mkd(){
      mkdir -p "$1" && cd "$1"
    }

###### Manually re-load config  
    source ~/.bashrc

---

##### 8. Aliases  
Aliases are shortcuts for commands used frequently.

Examples:

    alias se="sudo $EDITOR"
    alias ll="ls -alh"

---

##### 9. Add a Directory to PATH  
Common for storing personal scripts in:

`$HOME/.local/bin`

Add it to PATH inside `.bash_profile` or `.profile`:

    if [[ -d $HOME/.local/bin ]]; then
      export PATH="$HOME/.local/bin:$PATH"
    fi

---

#### Week 5

1. **The Shebang (`#!`)**  
> The first line of a script that specifies which interpreter should run the file.  
Examples:  
    #!/bin/bash  
    #!/usr/bin/env bash  
- Must be the **first line**  
- Allows running a script directly: `./scriptname`

---

2. **Running Scripts**  
Make a script executable:  
    chmod u+x scriptname  
Run it:  
    ./scriptname  
Scripts in `~/.local/bin` need `./` unless that directory is added to PATH.

---

3. **Quotes**  
- `"double quotes"` → **expand variables**  
- `'single quotes'` → **literal text**  

Examples:  
```bash
    echo "$HOME"   # expands  
    echo '$HOME'   # literal  
```

---

4. **Variables**  
Assign:  
    animal="wolf"  
Use:  
    echo "$animal"  

Environment variables:  
    export VAR=value  
    unset VAR  

Convention: environment variables use **UPPERCASE**.

---

5. **Special Variables**  

| Variable | Meaning |
|----------|---------|
| `$0` | Script name |
| `$1`, `$2` | Positional arguments |
| `$$` | Script’s PID |
| `$#` | Number of arguments |
| `$@` | All arguments (split) |
| `$*` | All args as one string |
| `$?` | Exit code of last command |

---

6. **Conditionals**  
Basic:  
```bash
    if [[ cond ]]; then
        commands
    fi  
```

With elif/else:  
```bash
    if [[ cond1 ]]; then
        ...
    elif [[ cond2 ]]; then
        ...
    else
        ...
    fi
```

---

7. **Tests (`[[ ]]`)**  
File tests:  
```bash
    [[ -f file ]]   # file exists  
    [[ -d dir  ]]   # directory exists  
```


Numeric/string tests:  
```bash
    [[ $x -ge 10 ]]  
    [[ "$name" == "bob" ]]  
```
Why `[[` is preferred: safer, supports patterns, supports regex, no need to quote variables.

---

8. **Case Statement**  
```bash
    case "$var" in
      A) echo "A";;
      B|b) echo "B or b";;
      [0-9]) echo "digit";;
      *) echo "default";;
    esac  
```

Patterns:  
- `*` anything  
- `?` one char  
- `[a-z]` range  
- `|` OR  

---

9. **Loops**  
```bash
For loop (list):  
    for x in a b c; do
        echo "$x"
    done  

Sequence:  
    for i in {1..5}; do echo "$i"; done  

C-style:  
    for ((i=0; i<10; i++)); do echo "$i"; done  

`break` → leave loop  
`continue` → next iteration  
```

---

10. **Arrays**  

```bash

Indexed array:  
    arr=("one" "two" "three")
    echo "${arr[0]}"
    echo "${arr[@]}"
    echo "${#arr[@]}"  

Associative array:  
    declare -A person
    person["name"]="Jan"
    person["age"]="31"
    echo "${person["name"]}"  
```

---

11. **Command Substitution**  
Store output of a command:  
    now=$(date)

---

12. **Troubleshooting**  
Enable debugging/tracing:  
    set -x  

Use **shellcheck**:  
    shellcheck scriptname  
Helps identify syntax errors, quoting issues, and best practices.

---

#### For-Loops

##### Looping over a LIST (created in advance)

```bash
list="apple banana cherry"

for item in $list; do
    echo "List item: $item"
done
```


##### Looping over a LIST (inline declaration)
```bash
for item in one two three; do
    echo "Inline list item: $item"
done
```


##### Looping over an ARRAY (created in advance)
```bash
fruits=("mango" "orange" "kiwi")

for fruit in "${fruits[@]}"; do
    echo "Array item: $fruit"
done
```

---

#### Week 6

Test 1 was here nothing to do

---

#### Week 7

##### 1. Shell Expansion Overview  
Bash performs seven types of expansion, in this order:

1. **Brace expansion**  
2. **Tilde expansion**  
3. **Parameter & variable expansion**  
4. **Command substitution**  
5. **Arithmetic expansion**  
6. **Word splitting**  
7. **Filename expansion**

Expansions happen after the command has been tokenized.

---

##### 2. Brace Expansion  
Generate sequences or comma-separated lists:

    echo {1..5..2}       # 1 3 5
    echo {a..f..2}       # a c e
    echo file{1..3}      # file1 file2 file3

---

##### 3. Tilde Expansion  
Unquoted `~` expands to user’s home directory:

    echo ~       # /home/username

---

##### 4. Parameter & Variable Expansion  
Basic form:

    var="hello"
    echo "$var"
    echo "${var}_world"

Length of string:

    name="Nathan"
    echo "${#name}"        # 6

Arrays:

    arr=(1 2 3 4)
    echo "${arr[@]}"       # all items
    echo "${#arr[@]}"      # number of items

Substring replacement:

    letters="abc"
    echo "${letters/abc/123}"   # 123

Indirect expansion (match variable names):

    prefix_a=one
    prefix_b=two
    echo ${!prefix_*}      # prefix_a prefix_b

String slicing:

    name="Nathan"
    echo "${name:0:2}"     # Na
    echo "${name:2:2}"     # th

File extension:

    file="notes.txt"
    echo "${file##*.}"     # txt

---

##### 5. Command Substitution  
Stores command output in a variable:

    now=$(date)
    path=$(realpath "$1")

---

##### 6. Arithmetic Expansion  
    echo "$(( (3 + 4) * 5 ))"   # 35

Bash math is limited—use `bc` or `awk` for complex math.

---

##### 7. Word Splitting  
Unquoted expansions split based on whitespace:

    nums1=( $(echo "one two three") )
    nums2=( "$(echo one two three)" )
    echo ${#nums1[@]} ${#nums2[@]}   # 3 1

Controlled by **IFS** (default: space, tab, newline).

---

##### 8. Filename Expansion (Globbing)
Patterns:

- `*` → any string  
- `?` → one character  
- `[abc]` → any listed char  
- `[1-3]` → range  

Examples (assume test dirs created):

    ls d*          # items starting with d
    ls dir?        # dir1 dir2
    ls *[1-2]      # items ending with 1 or 2

---

##### 9. Bash Functions  
Two forms (second is preferred):

    function foo { ... }

    foo() {
      commands
    }

Arguments:

    say_hi() {
      echo "hi $1"
    }
    say_hi "Bob"

Default argument values:

    greet() {
      local name="${1:-Guest}"
      echo "Hello, $name"
    }

Local variables:

    myfunc() {
      local x="local value"
      echo "$x"
    }

Capture output:

    result=$(myfunc)

Access all args:

    printall() {
      for item in "$@"; do
        echo "$item"
      done
    }

---

##### 10. Getting User Input (`read`)  
Basic:

    read name
    echo "Hello, $name!"

Inline prompt:

    read -p "Enter your name: " name

Silent (useful for passwords):

    read -s -p "Password: " pass

Flags:  
- `-p` prompt  
- `-s` silent input  

---

##### 11. Bash Heredocs  
Used to pass multi-line input to commands.

General form:

    command << EOF
    text
    more text
    EOF

Remote execution example:

    ssh user@host << EOF
      touch test-file
    EOF

Writing a file with heredoc:

    cat > newfile <<- EOF
        Line one
        Line two
    EOF

`<<-` strips leading tabs.

---

```bash
# write an array and a for loop that will loop over the array, printing each element.

fruits=("apple" "banana" "cherry")

for fruit in "${fruits[@]}"; do
    echo "Fruit: $fruit"
done
```

```bash
# Write a conditional that will check if a directory exists.

dir_path="/etc"

if [[ -d "$dir_path" ]]; then
    echo "Directory exists: $dir_path"
else
    echo "Directory does NOT exist: $dir_path"
fi
```

```bash
# Write a function that uses a local variable.

say_hi() {
    local name="Guest"
    echo "Hello, $name"
}

say_hi
```
 