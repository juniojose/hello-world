# Install [Apache](https://www.apache.org/) on WSL

Install Apache2:

| Bash |
| ---- |
| `sudo apt update` |
| `sudo apt install apache2` |

Start Apache:

| Bash |
| ---- |
| `sudo service apache2 start` |

Check if it's working: open a browser and access the `localhost` address. [You should see a Apache page](http://localhost/).

Removing the Apache index.html page:

| Bash |
| ---- |
| `cd /var/www/html` |
| `sudo rm index.html` |

Set file permission. Let's add our user to the apache group `www-data`:

| Bash |
| ---- |
| `sudo adduser $USER www-data` |

### Activating [mod_rewrite](https://httpd.apache.org/docs/current/mod/mod_rewrite.html)

| Bash |
| ---- |
| `sudo a2enmod rewrite` |
| `sudo service apache2 restart` |

### Enable the [SSL](https://httpd.apache.org/docs/2.4/ssl/ssl_howto.html) module

Enable the module in apache:

| Bash |
| ---- |
| `sudo a2enmod ssl` |
| `sudo service apache2 restart` |
| `sudo mkdir /etc/apache2/ssl` |

Creating a local certificate:

| Bash |
| ---- |
| `sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/apache2/ssl/apache.key -out /etc/apache2/ssl/apache.crt` |

Configuring apache to use this certificate:

- Open the `default-ssl.conf` file: `sudo nano /etc/apache2/sites-available/default-ssl.conf`

- Erase all file content and put:

````apache
<IfModule mod_ssl.c>
    <VirtualHost _default_:443>
        ServerAdmin webmaster@localhost
        ServerName localhost
        DocumentRoot /var/www/html
        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined  
        SSLEngine on
        SSLCertificateFile /etc/apache2/ssl/apache.crt   
        SSLCertificateKeyFile /etc/apache2/ssl/apache.key
        <FilesMatch "\.(cgi|shtml|phtml|php)$">
            SSLOptions +StdEnvVars
        </FilesMatch>
        <Directory /var/www/html>
            SSLOptions +StdEnvVars
            DirectoryIndex index.php
            AllowOverride All
            Order allow,deny
            Allow from all
        </Directory>
        BrowserMatch "MSIE [2-6]" nokeepalive ssl-unclean-shutdown downgrade-1.0 force-response-1.0       
        BrowserMatch "MSIE [17-9]" ssl-unclean-shutdown
    </VirtualHost>
</IfModule>
````

- Enable file settings:

| Bash |
| ---- |
| `sudo a2ensite default-ssl.conf` |
| `sudo service apache2 reload` |

- Check it:

Open a browser and access the `https://localhost` address.

The "Not secure" message will keep popping up, but that's not a problem because it only shows for me.
