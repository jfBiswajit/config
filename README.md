# Apache

**Redirect to public folder**

    <IfModule mod_rewrite.c>
      RewriteEngine on
      RewriteRule ^$ public/ [L]
      RewriteRule (.*) public/$1 [L]
    </IfModule>

**Redirect to public folder if page not found**

    <IfModule mod_rewrite.c>
      Options -Multiviews
      RewriteEngine On
      RewriteBase /web_site/public
      RewriteCond %{REQUEST_FILENAME} !-d
      RewriteCond %{REQUEST_FILENAME} !-f
      RewriteRule  ^(.+)$ index.php?url=$1 [QSA,L]
    </IfModule>

**Prevent folder access**

    Options -Indexes

**Rewrite queries (symfony)**

    <IfModule mod_rewrite.c>
       RewriteEngine On
       RewriteCond %{REQUEST_URI}::$1 ^(/.+)/(.*)::\2$
       RewriteRule ^(.*) - [E=BASE:%1]
       RewriteCond %{REQUEST_FILENAME} -f
       RewriteRule .? - [L]
       RewriteRule .? %{ENV:BASE}/index.php [L]
    </IfModule>

# Xaamp

**Login**

- with pass `mysql -h localhost -u root -p`
- no pass `mysql -u root`

**Change localhost directory**

- go to `C:\xampp\apache\conf\httpd.conf`
- gearch for `DocumentRoot` and replace loaction

**Create Vhost**

Xampp path `C:\xampp\apache\conf\extra\httpd-vhosts.conf` 

    <VirtualHost *:80>
       DocumentRoot "C:\xampp\htdocs\Symfony\public"
       ServerName symfony.test
    </VirtualHost>

vhost: `C:\Windows\System32\drivers\etc\hosts`

    127.0.0.1 localhost.test


**Debugger**
- go to `https://xdebug.org/wizard` paste phpinfo()
- download  `dll` file and move to `C:\xampp\php\ext`
-  go to `C:\xampp\php\php.ini` and paste  

    [XDebug]
    xdebug.remote_enable  = 1
    xdebug.remote_autostart  = 1
    zend_extension  =  "c:\xampp\php\ext\php_xdebug.dll"

- restarted apache 

**Speed up**

Go to  `C:\xampp\php\php.ini` then modifi following settings:

-   set  `realpath_cache_size = 4M`  (or more)
-   disabled  `XDebug`  completely (test with  `phpinfo`)
-   realpath_cache_ttl=7200
-   enabled and set  `OPcache`  (or APC) correctly
-   restarted apache 

# Github

**Step: 1 (Local)**

- name: `git config --global user.name "Biswajit Biswas"`
- email: `git config --global user.email "jfbiswajit@gmail.com"`
- show config details: `git config --global --list`

**Step: 2 (Remote)**

- go to root directory: `cd ~`
- create ssh directory: `mkdir .ssh`
- generate Key: `ssh-keygen -t rsa -C "jfbiswajit@gmail.com"`
- copy the SSH key from `id_rsa.pub`
- now go to github setting and click SSH and add new SSH with copied key

**Step: 3 (Test connection)**

- test connection: `ssh -T git@github.com`


**Terminal color**

`notepad ~/.bashrc` (creat new one if doesn't exist)

    alias ls='ls --color' # list with color
    alias la='ls -alF' # list all

paste and save
