Docker configuration for Symfony 4
====

Php 7.2, Nginx, Mysql, Xdebug and composer inside app container

- put init sql dump into the folder "mysql/dump" if you want to create data base from it  



Setup
----

1) `git clone https://github.com/kvush/docker-symfony-4.git project-name`
2) `cp docker.env.example .docker.env`
3) Edit docker.env according to your needs
4) `docker-compose up -d`
5) `docker-compose exec app composer install` 