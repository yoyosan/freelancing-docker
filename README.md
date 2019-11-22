# No BS Docker services for freelancing

## About

Based on Laradock, you can use this folder to start only what you need
for your freelancing services.

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

Start it up:

```bash
docker-compose up -d
```

Rebuild everything to update service versions:

```
docker-compose down && docker-compose build && docker-compose up -d
```
