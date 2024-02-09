**Problem 1:** Running `php artisan tinker` throwing `Unable to create PsySH runtime directory. Make sure PHP is able to write to /run/user/4675 in order to continue` error in shared hosting example (cpanel)

**Solution:** Run following commands:

 1. `mkdir ~/.config/psysh/ -p`
 2. `echo "<?php
return [
    'runtimeDir' => '~/tmp'
];" >> ~/.config/psysh/config.php`
---
**Problem 2** Hosting laravel folder in `public_html` folder of Shared Hosting (ex: cpanel)

**Solution:** Add `.htaccess` file in root directory of laravel (`public_html`) with following contents

    <IfModule mod_rewrite.c>

    <IfModule mod_negotiation.c>

        Options -MultiViews -Indexes

    </IfModule>
    RewriteEngine On

    RewriteCond %{REQUEST_URI} !^/public/

    RewriteRule ^(.*)$ /public/$1 [L,QSA]
    
    </IfModule>
    
    <Files .env>
    order allow,deny
    Deny from all
    </Files>
