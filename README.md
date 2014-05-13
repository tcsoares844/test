# Alice

Alice is the front-end application for web and mobile using Symfony 2.

### SYSTEM REQUIREMENTS

Alice requires PHP 5.5.0 or later; we recommend using the latest PHP version whenever possible.

### INSTALLATION

Clone Alice repository into your work directory with HTTP or SSH method:

```shell
$ cd path/to/work-directory
```

Using HTTP method:

```shell
https://github.com/FreakPay/alice.git
```
Using SSH method:

```shell
$ git clone git@github.com:FreakPay/alice.git
```

After cloning repository into your work directory you need to install dependencies of project with [Composer](https://getcomposer.org/ "Composer: Dependency Manager for PHP") the package manager used by modern PHP applications and the only recommended way to install Alice.

To update composer itself to the latest version, just run the `self-update` command. It will replace your `composer.phar` with the latest version.

```shell
$ php composer.phar self-update
```

To install dependencies of your ptoject just run the `insttall`. The `install` command reads the `composer.json` file from the current directory, resolves the dependencies, and installs them into `vendor`.

```shell
$ php composer.phar install
```

If there is a `composer.lock` file in the current directory, it will use the exact versions from there instead of resolving them. This ensures that everyone using the library will get the same versions of the dependencies.
In order to get the latest versions of the dependencies and to update the `composer.lock` file, you should use the `update` command.

```shell
$ php composer.phar update
```

You have two ways to run your project. Run [built-in](http://www.php.net/manual/en/features.commandline.webserver.php) web server or run the application with [Apache](http://www.apache.org/ "The Apache Software Foundation").

For run built-in web server, execute the following command:

```shell
$ php -S 127.0.0.1:8888 -t public public/index.php
```

For run with apache you need to create a Virtual Host into Apache configuration. Copy and paste the following lines into your virtual host file:

```shell
<VirtualHost *:80>
    ServerName alice.dev
    DocumentRoot /path/to/work-directory/alice/public/

    SetEnv APPLICATION_ENV "development"

    <Directory /path/to/work-directory/alice/public/>
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

The files in this archive are released under The MIT License (MIT). You can find a copy of this license in [LICENSE.txt](https://github.com/freakpayment/alice/blob/master/README.md).
