# Web Programming
### OS1 - 2112 - TICA - TP2-W7-S11

## 2402001636

<br>

```bash
$ docker run --rm --interactive --tty --volume "$PWD":/app composer create-project --prefer-dist laravel/laravel TP2-W7-S11$
$ cd TP2-W7-S11$/
$ docker run --rm --interactive --tty --volume "$PWD":/app composer require laravel/breeze --dev
$ docker run -v "$PWD":/usr/src/app -w /usr/src/app node npm --loglevel=info install
$ docker run -v "$PWD":/usr/src/app -w /usr/src/app node npm --loglevel=info run dev
$ docker run --rm --interactive --tty --volume "$PWD":/app composer require anhskohbo/no-captcha --ignore-platform-req=ext-gd
```

<br>

```bash
$ docker network create mysql-net
$ docker run --network mysql-net --name mysql -e MYSQL_ROOT_PASSWORD=binus -e MYSQL_DATABASE=tp2 -e MYSQL_USER=binus -e MYSQL_PASSWORD=binus -p 3306:3306 -d mysql:latest
$ docker inspect mysql | grep IPAddress

$ docker run --network mysql-net -it --rm mysql mysql -hmysql -ubinus -p
```

<br>

```ini
DB_CONNECTION=mysql
DB_HOST=172.18.0.2
DB_PORT=3306
DB_DATABASE=tp2
DB_USERNAME=binus
DB_PASSWORD=binus
```

<br>

```bash
$ docker run --network mysql-net -it --rm -v "$PWD":/app -p 8000:8000 php bash
root@590a401d877e:/# cd /app/
root@590a401d877e:/app# docker-php-ext-install mysqli pdo pdo_mysql
root@590a401d877e:/app# apt update && apt install -y zlib1g-dev libpng-dev
root@590a401d877e:/app# php artisan breeze:install
root@590a401d877e:/app# php artisan migrate
root@590a401d877e:/app# php artisan serve --host 0.0.0.0
```

<br>

```bash
$ heroku login
$ heroku git:remote -a <app>
$ git push heroku master
$ heroku config:set APP_NAME="Aplikasi Login Form"
$ heroku config:set APP_KEY=<key>
$ heroku config:set DB_CONNECTION=mysql
$ heroku config:set DB_HOST=<host>
$ heroku config:set DB_PORT=<port>
$ heroku config:set DB_DATABASE=<database>
$ heroku config:set DB_USERNAME=<username>
$ heroku config:set DB_PASSWORD=<password>
$ heroku config:set NOCAPTCHA_SITEKEY=<sitekey>
$ heroku config:set NOCAPTCHA_SECRET=<secretkey>
$ heroku run php artisan migrate
```
