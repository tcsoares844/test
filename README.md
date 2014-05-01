# Alice

Alice is front-end application for web and mobile using Zend Framework 2.

### SYSTEM REQUIREMENTS

Alice requires PHP 5.5.0 or later; we recommend using the latest PHP version whenever possible.

### INSTALLATION

[Composer](https://getcomposer.org/ "Composer: Dependency Manager for PHP") is the package manager used by modern PHP applications and the only recommended way to install Alice. To install Composer on your Linux or Mac system, execute the following commands:

```shell
$ curl -sS https://getcomposer.org/installer | php
```

You have two ways to run your project. Run built in PHP server or run the application with [Apache](http://www.apache.org/ "The Apache Software Foundation").

If your choos is run built in server, execute the following commands:

```shell
$ cd path/to/install
```

```shell
$ php -S 127.0.0.1:8888 -t public public/index.php
```

For run Alice with apache you need to create a Virtual Host into Apache configuration. Copy and paste the following lines:

```shell
#Virtual Host for Alice:
<VirtualHost *:80>
    ServerName alice.dev
    DocumentRoot /var/www/alice/public/

    SetEnv APPLICATION_ENV "development"

    <Directory /var/www/alice/public/>
        DirectoryIndex index.php
        AllowOverride All
        Order allow,deny
        Allow from all
    </Directory>

    ErrorLog /var/log/apache2/alice_error.log
    CustomLog /var/log/apache2/alice.log combined
</VirtualHost>
```

### LICENSE

The files in this archive are released under The MIT License (MIT). You can find a copy of this license in LICENSE.txt.
