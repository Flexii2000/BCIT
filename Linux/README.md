€## Test 2 preparation

#### Content Overview
- cumulative tests
- all topics starting at week 1 until week 11 can and will be part of the test

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


## Final exam preparation

#### Content Overview
- cumulative exam
- all topics covered in the entire term can and will be part of the exam
 