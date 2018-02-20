# PHP-FPM Docker image for Drupal

Docker image for a php-fpm container crafted to run Drupal based applications.

## Specifications:

* PHP 7.1
* OpenSSL PHP Extension
* Mbstring PHP Extension
* Tokenizer PHP Extension
* Curl PHP extension
* JSON PHP extension
* Dom PHP Extension
* Fileinfo PHP Extension
* Hash PHP Extension
* Iconv PHP Extension
* Intl PHP Extension
* Zip PHP Extension
* PDO PHP Extension
* MySQL and PgSQL Support via MySQLi and PgSQL PHP Extensions
* SimpleXML and XML PHP Extension
* GD2 PHP Extension
* OP Cache PHP Extension
* Composer
* PHP ini values for SilverStripe (see [`silverstripe.ini`](/silverstripe.ini))
* xDebug (PHPStorm friendly, see [`xdebug.ini`](/xdebug.ini)) Disabled by default.
* `drush` alias created to run Drupal CLI with `docker-compose exec [service_name] drush`.

## Tags available:

When calling the image you want to use within your `docker-compose.yml` file,
you can specify a tag for the image. Tags are used for various versions of a
given Docker image. By default, `latest` is the one used when no tag is specified.

* `latest` which is using PHP 7.1 for Drupal 8.
* `7.1` for Drupal 8 using PHP 7.1.

## docker-compose usage:

```yml
version: '2'
services:
    php-fpm:
        image: cyberduck/php-fpm-drupal(:<optional-tag>)
        environment:
            - XDEBUG="true" # optional: "false" by default
        volumes:
            - ./:/var/www/
            - ~/.ssh:/root/.ssh # can be useful for composer if you use private CVS
        networks:
            - my_net #if you're using networks between containers
```
