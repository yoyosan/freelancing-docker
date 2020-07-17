# No BS Docker services for freelancing

## About

Based on [Laradock](https://github.com/laradock/laradock) but without all the BS services,
you can use this folder to start only what you need for your freelancing services.

What's included?
* Nginx from Alpine latest(default)
* Apache from Ubuntu 18.04(optional)
* PHP 7.3 with FPM
* Maria DB latest
* Mailhog latest
* Laravel PHP config

## Installation

```bash
cp env-example .env
# edit accordingly
```

### Switching to Apache

Use the following snippet in `docker-compose.yml` to use Apache:

```dockerfile
  web:
    build:
      context: ./apache
    working_dir: /var/www
    volumes:
      - ../freelancing/:/var/www
      - ./apache/logs:/var/log/apache2
      - ./apache/sites:/etc/apache2/sites-available
    ports:
      - "80:80"
    depends_on:
      - php-fpm
```

## Usage

First, make sure your projects are in a `../freelancing` folder.

Start it up:

```bash
docker-compose up -d
```

Rebuild everything to update service versions:

```
docker-compose down && docker-compose build --pull --force-rm && docker-compose up -d
```

Add new sites:

Just add a new file based on `nginx/sites/sample.conf.example` in the `nginx/sites/` folder.

and then do a:

```
docker-compose restart
```
