Docker for Gibbon with Nginx

Description
===========
PHP Version: 7.3
Web server: Nginx
Database: MySQL 5.7

Pre-requisit
===========
1) Install docker at
2) Install docker-compose
3) Install git

Required php extensions
=======================
gettext
curl
gd

Set up
=======
1) Clone docker project from git repository: git clone my-repository
2) Clone gibbon project into root folder: git clone
3) Make a copy of .env_dist to .env: cp .env_dist .env
4) Update variables from .env with values corresponding to your environment
5) Run docker-composer build from root folder
6) Run docker-composer up -d from root folder
7) Go to localhost:8081

Supported versions of gibbon:
============================

Gibbon 1.17.0

Language Supported
==================

1) SSH to the php container
2) https://people.debian.org/~schultmc/locales.html


Folder structure in depth
=========================

/root/docker/nginx => nginx configuration with Dockerfile
/root/docker/php-fpm => php-fpm configuration for nginx via Dockerfile

Theme
=====
The theme by default was modified
