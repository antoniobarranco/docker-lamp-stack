# Simple & Quick Docker LAMP Stack

## Purpose

This is a simple and quick LAMP Stack for development, built on Docker using Docker Compose.

You can use this to launch both edge and legacy environments, so you can set any version of PHP, MYSQL/MariaDB, and PHPMyAdmin.

The purpose is to create an enviroment in a quick way, avoiding volumes and storing on binded filesystem the database information as well the web root.

You can customize various aspects on `.env` file, for example, the PHP version and PHP loaded modules, the MYSQL or MariaDB version and the release of PHPMyAdmin.

## Configuration

Instead of using `docker-compose.yml` file, all common configs will be set on `.env` file. You can also adjust params on `docker-compose.yml` as you need.

There are two aditional Dockerfiles on docker folder. These are used to setup the containers on creation and you can add all you need on these.

If you dont do any changes your default enviroment will be:

- PHP 8.1.0
- MariaDB 10.7.1
- Latest PHPMyAdmin

PHP will be loaded with these enabled extensions:

- curl
- mysqli
- pdo
- pdo_mysql
- [You can add more on `Dockerfile` at `docker/php` folder]

And Apache will be set to use `mod_rewrite`

## How to use

You only need to configure the environment to your preferences or needs as explained in the previous section.

Your MySQL/MariaDB data will stored on `mysql` folder, so don't delete it. These data will remain uppon container stops, restarts and even deletions. Take care about database versions changes after creating the environment, sometimes data is not compatible between versions.

Your website root is placed on `www` folder. Feel free to store on it anyone you need.

To start your enviroment you need simply to execute the following command at main folder (where docker-compose.yml are):

`docker-compose up`

Your website will be at: 

http://localhost

And your PHPMyAdmin is at:

http://localhost:8080/

And that's all!!