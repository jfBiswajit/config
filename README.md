# Xaamp

**Xampp (Pass):** `mysql -h localhost -u root -p`

**Xampp (No pass):** `mysql -u root`

**Change localhost directory:**

- Go to `C:\xampp\apache\conf\httpd.conf`
- Search for `DocumentRoot` and replace loaction

# Gitbash (Config)

**Step: 1 (Local)**

- Name: `git config --global user.name "Biswajit Biswas"`
- Email: `git config --global user.email "jfbiswajit@gmail.com"`
- show config details: `git config --global --list`

**Step: 2 (Remote)**

- Go to root directory: `cd ~`
- Create ssh directory: `mkdir .ssh`
- Generate Key: `ssh-keygen -t rsa -C "jfbiswajit@gmail.com"`
- Copy the SSH key from `id_rsa.pub`
- Now go to github setting and click SSH and add new SSH with copied key

**Step: 3 (Test connection)**

- Test connection: `ssh -T git@github.com`


**Terminal color**

`notepad ~/.bashrc` (creat new one if doesn't exist)

**step:2**

    alias ls='ls --color' # list with color
    alias la='ls -alF' # list all

Paste and save
