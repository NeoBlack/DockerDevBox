![DevelopmentBox based on Docker](https://raw.githubusercontent.com/NeoBlack/DockerDevBox/master/assets/logo.png)

# DockerDevBox

1) copy `.env.example` into `.env` and adjust the parameters if you want.

2) Start the docker box:

run `docker-compose up`

or for starting it in the background (detached):

run `docker-compose up -d`

## What is included?
- PHP 5.6
- PHP 7.0
- PHP 7.1
- MySQL (latest)
- Elasticsearch
- Redis
- Mailhog
- Shell-in-a-box
- GraphicsMagick

## What is missing?
- xdebug
- xhprof / blackfire

## Bash into your containers
Run one of the following commands to access your containers:

- `docker-compose exec <container-name> bash`
- `docker-compose exec nginx bash`
- `docker-compose exec php56 bash`
- `docker-compose exec php70 bash`
- `docker-compose exec php71 bash`
- `docker-compose exec mysql bash`
- `docker-compose exec es bash`
- `docker-compose exec redis bash`
- `docker-compose exec mail bash`

## SSH in your containers
You can bash into your containers and use your SSH keys from ~/.ssh

## Shell-in-a-box
Shell access from your browser use `dev` as username and password:

- http://shell.devbox.21r.de

## Database
You can connect from PHP to the MySQL database with the hostname `mysql` on port `3306`.
You can also connect from host system to your MySQL database with hostname `127.0.0.1` on port `3306`.

- MySQL root username: root
- MySQL root password: dev
- MySQL dev username: dev
- MySQL dev password: dev

## Nginx
You have one default dynamic host configuration. You can use any subdomain of `*.devbox.21r.de` e.g. `http://test.devbox.21r.de`.
This domain has the DocumentRoot in your home directory: `~/work/test/Web/`

## PHP Versions
Default PHP version is `7.0` but you can switch the PHP version by prefix your subdomain:

Examples:
- http://test.devbox.21r.de [PHP 7.0]
- http://php56.test.devbox.21r.de [PHP 5.6]
- http://php70.test.devbox.21r.de [PHP 7.0]
- http://php71.test.devbox.21r.de [PHP 7.1]

## Elasticsearch
The following plugins are installed:
- http://elastic.devbox.21r.de/_plugin/head/
- http://elastic.devbox.21r.de/_plugin/kopf/

## Redis
Redis is running on port 6379

## Mailhog
Mailhog catches all mails send by PHP or over `mail:1025` via SMTP.

You can access the nice looking web mail interface under:

- http://mail.devbox.21r.de
