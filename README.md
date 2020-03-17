# laravel-Dockerization
Sample to dockerize a laravel app
ref=https://github.com/changeweb/Unifiedtransform

# Framework used

- Laravel 5.5
- Bootstrap 3.3.7

## Server Requirements

- PHP >= 7.1.0
- OpenSSL PHP Extension
- PDO PHP Extension
- Mbstring PHP Extension
- Tokenizer PHP Extension
- XML PHP Extension

## How to Start
### Using a Container:

**Anyone having trouble related to `mysql-client`, PHP 7.3 needs mariadb instead of mysql.** See issue [#192](https://github.com/changeweb/Unifiedtransform/issues/192)

**[Docker](https://www.docker.com/)** is now supported.

You need to change Docker configuration files according to your need.

- Change following lines in `docker-compose.yml`

      MYSQL_ROOT_PASSWORD: your password
      MYSQL_USER: root
      MYSQL_PASSWORD: your password

- To run this software in Docker containers run `sudo docker-compose up -d`.
- Then run `sudo docker container ls --all`. Copy **Nginx** Container ID.
- Then run `sudo docker exec -it <container id> bash`
- Run `cp .env.example .env` and change following lines in `.env` file
   ```sh
   DB_HOST=db
   DB_PORT=3306
   DB_DATABASE=school
   DB_USERNAME=root
   DB_PASSWORD=your password
   ```
- Run `composer install`
- Run `php artisan key:generate`
- Run `php artisan migrate:fresh --seed`
- Visit `http://localhost:80`.

