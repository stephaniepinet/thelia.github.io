---
layout: home
title: installation
sidebar: installation
lang: en
---

<div class="page-header">
    <h1>Requirements</h1>
</div>

* php 5.4
    * Required extensions :
        * PDO_Mysql
        * mcrypt
        * intl
        * gd
        * curl
    * safe_mode off
    * memory_limit at least 150M, preferably 256.
    * post\_max\_size 20M
    * upload\_max\_filesize 2M
* apache 2
* mysql 5

If you use Mac OSX, it still doesn't use php 5.4 as default php version... There are many solutions for you :

* use linux (the best one)
* use last MAMP version and put the php bin directory in your path  :

```bash
export PATH=/Applications/MAMP/bin/php/php5.4.x/bin/:$PATH
```

* configure a complete development environment : [http://php-osx.liip.ch](http://php-osx.liip.ch)
* use a virtual machine with vagrant and puppet : [https://puphpet.com](https://puphpet.com)

<div class="page-header">
    <h1>Installation</h1>
</div>


## Download Thelia 2

``` bash
$ git clone https://github.com/thelia/thelia.git
$ cd thelia
$ wget http://getcomposer.org/composer.phar
$ php composer.phar install
```

Finish the installation using cli tools :

``` bash
$ php Thelia thelia:install
```

You just have to follow all instructions.

## How to create an admin account ?

```bash
$ php Thelia admin:create
```

## How to insert fake data ?

For a demo with fake but realistic products

``` bash
$ php install/import.php
```

For dev data

```bash
$ php install/faker.php
```

(composer must be install [`globally`](http://getcomposer.org/doc/00-intro.md#globally))
## How to reset my database


```bash
$ ./reset_install.sh
```

this task reload the database, insert fake data using faker script and create an admin with thelia2 as username and password

<div class="page-header">
    <h1>Usage</h1>
</div>

Consult the page : http://localhost/thelia/web/index_dev.php

You can create a virtual host and choose web folder for root directory.

To run tests (phpunit required) :

``` bash
$ phpunit
```

We still have lot of work to achieve but enjoy this part.