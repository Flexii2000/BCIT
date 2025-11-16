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

