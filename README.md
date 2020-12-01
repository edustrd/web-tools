# web-tools

### Install
```
clone the project
npm install
npm run dev
```

### Virtual Host Ubuntu
```
sudo a2ensite web-tools.com.br.conf

sudo vim /etc/apache2/sites-available/web-tools.com.br.conf

<VirtualHost *:80>
        ServerAdmin admin@web-tools.com.br
        ServerName web-tools.com.br
        ServerAlias www.web-tools.com.br
        DocumentRoot /var/www/web-tools/public

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        <Directory "/var/www/web-tools/public">
                AllowOverride All
        </Directory>
</VirtualHost>

:wq

sudo systemctl reload apache2.service

sudo vim /etc/hosts
127.0.0.1       web-tools.com.br
:wq

sudo service apache2 reload
```
[localhost](http://web-tools.com.br/)
