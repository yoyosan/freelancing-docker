# No BS Docker services for freelancing

## About

Based on [Laradock](https://github.com/laradock/laradock) but without all the BS services,
you can use this folder to start only what you need for your freelancing services.

What's included?
* Apache 2.4
* PHP 7.3 with FPM
* Maria DB latest
* Laravel PHP config

## Installation

```bash
cp env-example .env
# edit accordingly
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

Just add a new file based on `apache/sites/sample.conf.example` in the `apache/sites/` folder.

and then do a:

```
docker-compose restart
```
