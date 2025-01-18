## Symfony Version 1.4.6 Template:

Symfony Version: [1.4.6](https://symfony.com/legacy)<br/>
Xampp + PHP 5.6.8: [v3.2.1](https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/5.6.8/xampp-win32-5.6.8-0-VC11.7z/download)
MYSQL [5.7] (https://dev.mysql.com/downloads/windows/installer/5.7.html)

### Web Server Configuration

Locate and open the `httpd.conf` configuration file and add the following configuration at the end:

Update `C:\xampp\apache\conf\httpd.conf`:

```
<VirtualHost *:80>
    ServerName dev.symfony.localhost
    DocumentRoot "C:/xampp/htdocs/symfony-1.4.6-template/web"
    DirectoryIndex index.php
    <Directory "C:/xampp/htdocs/symfony-1.4.6-template/web">
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Require all granted
    </Directory>
    Alias /sf "C:/xampp/htdocs/symfony-1.4.6-template/lib/vendor/symfony/data/web/sf"
    <Directory "C:/xampp/htdocs/symfony-1.4.6-template/lib/vendor/symfony/data/web/sf">
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```

Update `C:\Windows\System32\drivers\etc\hosts`:

```
127.0.0.1 dev.symfony.localhost
```

Run Apache Server and Access `dev.symfony.localhost` in the browser.