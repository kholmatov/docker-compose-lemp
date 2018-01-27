# Dockerized LEMP Environment

## How do I use it?
1. Extract your application to: `./app`
2. Run `make build` to pull images
3. Run `make run` to run docker containers
3. Configure your application to use the following DB settings:
    * Host / Server: db
    * Username: root
    * Password: password
    * Database Name: application

### Need to install PHP Modules?
It's really simple. Edit: `./php/Dockerfile` and add the module name to a new
`RUN` instruction line. For example to add the `redis` PHP module:
```
RUN /usr/local/bin/docker-php-ext-install pdo pdo_mysql

RUN /usr/local/bin/docker-php-ext-install redis
```

# Makefile
To make things a little easier there's a Makefile that helps make various tasks a
bit quicker / safer:

* `make build` docker-compose build
* `make run` docker-compose up
* `make start` docker-compose up -d
* `make stop` docker-compose stop
