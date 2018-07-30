# Docker with FuelPHP
* Download source code
```
$ git clone https://github.com/minhnv2306/docker-fuel.git
$ cd docker-fuel
$ git clone https://github.com/minhnv2306/authencation_fuelphp.git blog
```
* Run docker-compose
```
$ docker-compose up --build
```
* Composer and npm install
```
$ docker ps
$ docker exec -i -t {container_PHP} /bin/bash
$ cd blog
$ chmod 777 -R .
$ composer install
$ npm install 
$ npm run dev
```
* Config database

View host
```
$ docker exec -i -t {container_DB} cat /etc/hosts
```
Edit file config 
```
/blog/fuel/app/db.php
/blog/fuel/config/development/db

connection' => array (
    'hostname'       => 'IP_address_DB',
    'port'           => '3306',
    'database'       => 'mydb',
    'username'       => 'root',
    'password'       => 'root',
),
```
* Migrate database
```
$ docker ps
$ docker exec -i -t {container_PHP} /bin/bash
$ cd blog
$ php oil refine migrate
```
* Test
```
http:://localhost:8696
```
