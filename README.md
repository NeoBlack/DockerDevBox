# DockerDevBox

run `docker-compose up`

or for starting it in the background (detached):

run `docker-compose up -d`

## TODOs, What's missing?
- MailHog container
- Solr container
- Add GraphicsMagick / ImageMagick
- Add static external IP address for the nginx container instead of 0.0.0.0

## What is included?
- PHP 5.6
- PHP 7.0
- PHP 7.1
- MySQL (latest)
- Elasticsearch
- Redis

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

## SSH in your containers
You can bash into your containers and use your SSH keys from ~/.ssh

## Database
You can connect from PHP to the MySQL database with the hostname `mysql` on port `3306`.
You can also connect from host system to your MySQL database with hostname `127.0.0.1` on port `3306`.

- MySQL root username: root
- MySQL root password: dev
- MySQL dev username: dev
- MySQL dev password: dev

## PHP Versions
Default PHP version is `7.0` but you can switch the PHP version by prefix your subdomain:

Examples:
- http://test.local.typo3.org [PHP 7.0]
- http://php56.test.local.typo3.org [PHP 5.6]
- http://php70.test.local.typo3.org [PHP 7.0]
- http://php71.test.local.typo3.org [PHP 7.1]

## Elasticsearch
The following plugins are installed:
- http://elastic.local.typo3.org/_plugin/head/
- http://elastic.local.typo3.org/_plugin/kopf/

## Redis
Redis is running on port 6379

## Additional Setup
At the moment you need some additional setup:

### 1) Create a folder
`~/work/test.local.typo3.org/`

### 2) /etc/hosts entries

Add the following entries to your `/etc/hosts` file

```
0.0.0.0 test.local.typo3.org
0.0.0.0 php56.test.local.typo3.org
0.0.0.0 php70.test.local.typo3.org
0.0.0.0 php71.test.local.typo3.org
0.0.0.0 elastic.test.local.typo3.org
```