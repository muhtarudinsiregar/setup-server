## Instalasi
    1. apt-get update
    2. apt-get install mysql-server
    3. apt-get install php libapache2-mod-php php-mcrypt php-mysql php-mbstring php-dom
    4. apt-get install git
    5. apt-get install curl
    

## Step by step
### 1. clone repo to var/www/http/html
### 2. set etc/apache2/sites-enable
```
<VirtualHost *:80>
    ServerName coba.demo.example.com  //ip
    DocumentRoot /var/www/html/book-workshop/public
    
    <Directory /var/www/html/book-workshop/public/>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
  ```
  
### 3. in var/www/html/book-workshop, run command : 
    curl —output composer.phar https://getcomposer.org/download/1.3.2/composer.phar
    
### 4. Install packages
    php composer.phar install

### 5. `sudo a2enmod rewrite` to activate mod rewrite, then restart the apache

### 6. chown -R www-data:www-data bootstrap/ storage/

### 7. restart apache
    service apache2 restart
    
### 8. if your routes not found, repeat step 6 and 7.
