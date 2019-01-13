Docker for Gibbon

Description
===========
This project provide a dockerized version of Gibbon (https://docs.gibbonedu.org) easy to install. It is configured to run the following infrastructure:
- PHP Version: 7.3
- Web server: Nginx
- Database: MySQL 5.7

Pre-requisit
============
To run this project you need first to install the following softwares:
1) Install docker: https://www.docker.com/get-started
2) Install docker-compose: https://docs.docker.com/compose/install/
3) Install git: https://git-scm.com/downloads

Install and run
===============
1) Clone docker project: git clone https://github.com/sylwn/gibbon-docker.git
2) Go in root folder and download Gibbon: cd gibbon-docker && wget "https://github.com/GibbonEdu/core/archive/v16.0.01.zip"
3) Unzip Gibbon: unzip -a v16.0.01.zip
4) Make a copy of env variables file and update it (accordingly to your env): cp .env_dist .env
6) Build docker containers: docker-composer build
7) Run conatiners: docker-composer up -d
8) Visit the project: your.local.domain:port (default: gibbon.local:8081)

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
