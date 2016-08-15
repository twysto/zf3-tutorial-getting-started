# ZF3 Tutorial - Getting started

## Description

This is the first part of the "MVC Tutorials" series that you can find here in the official ZF3 documentation :
[https://docs.zendframework.com/tutorials](https://docs.zendframework.com/tutorials)

Getting Started with Zend Framework 3 is just as fast as following this few steps.

## Installation

```bash
$ cd /to/projects/root/folder
$ git clone https://github.com/twysto/zf3-tutorial-getting-started.git
$ cd zf3-tutorial-getting-started
$ composer update
```

## Create and configure database

Create a database and import this MySQL schema.

```sql
CREATE TABLE album (id INTEGER PRIMARY KEY AUTO_INCREMENT, artist varchar(100) NOT NULL, title varchar(100) NOT NULL);
INSERT INTO album (artist, title) VALUES ('The Military Wives', 'In My Dreams');
INSERT INTO album (artist, title) VALUES ('Adele', '21');
INSERT INTO album (artist, title) VALUES ('Bruce Springsteen', 'Wrecking Ball (Deluxe)');
INSERT INTO album (artist, title) VALUES ('Lana Del Rey', 'Born To Die');
INSERT INTO album (artist, title) VALUES ('Gotye', 'Making Mirrors');
```

Then edit the file `./config/autoload/global.php` and edit the connection string with your own database name, user name and password.

```php
'db' => [
    'driver' => 'PDO',
    'dsn' => sprintf('mysql:host=%s;port=%s;dbname=%s', 'localhost', '3306', 'zftutorial'),
    'user' => 'root',
    'password' => '',
],
```

## Run with the PHP built-in server

```bash
$ php -S 127.0.0.1:8080 -t public/ public/index.php
```

Then open your favorite browser and navigate to http://127.0.0.1:8080

## Learn more

If you already start to read this "Getting Started with Zend Framework" tutorial, you've noticed it is based on the [ZendApplicationSkeleton](https://github.com/zendframework/ZendSkeletonApplication).
To learn more about the possibilities it offers, check this repository README file.