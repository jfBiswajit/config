# Xaamp

**Login**

- With pass `mysql -h localhost -u root -p`
- No pass `mysql -u root`

**Change localhost directory**

- Go to `C:\xampp\apache\conf\httpd.conf`
- Search for `DocumentRoot` and replace loaction

**Create Vhost**

Xampp path `C:\xampp\apache\conf\extra\httpd-vhosts.conf` 

    <VirtualHost *:80>
       DocumentRoot "C:\xampp\htdocs\Symfony\public"
       ServerName symfony.test
    </VirtualHost>

Vhost: `C:\Windows\System32\drivers\etc\hosts`

    127.0.0.1 localhost.test


**Debugger**
- Go to `https://xdebug.org/wizard` paste phpinfo()
-   Download  `dll` file and move to `C:\xampp\php\ext`
-  Go to `C:\xampp\php\php.ini` and paste  `[XDebug]
xdebug.remote_enable  = 1
xdebug.remote_autostart  = 1
zend_extension  = C:\xampp\php\ext\php_xdebug-2.9.2-7.4-vc15-x86_64.dll`
- Restart Xampp server

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

    alias ls='ls --color' # list with color
    alias la='ls -alF' # list all

Paste and save



