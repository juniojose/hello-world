# Install [PHP](https://www.php.net/) on WSL

| Bash |
| ---- |
| `sudo apt install php libapache2-mod-php php-mysql php-mail php-imagick php-intl` |

Check it:

| Bash |
| ---- |
| `sudo service apache2 restart` |
| `cd /var/www/html` |
| `sudo nano index.php` |

| [Nano](https://www.nano-editor.org/) |
| ---- |
| `<?php phpinfo(); ?>` |

Save and exit nano. Open a browser and access the `localhost` address.

Remove phpinfo index.php:

| Bash |
| ---- |
| `sudo rm index.php` |
