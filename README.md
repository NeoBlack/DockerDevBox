# Docker DevBox

run `docker-compose up`

or for starting in background (detached):

run `docker-compose up -d`

## What is included?
- PHP 5.6
- PHP 7.0
- PHP 7.1
- MySQL (latest)
- Elasticsearch
- Redis

## Database
You can connect from PHP to the MySQL database with the hostname `mysql` on port `3306`.
You can also connect from host system to your MySQL database with hostname `127.0.0.1` on port `3306`.

- MySQL root username: root
- MySQL root password: dev
- MySQL dev username: dev
- MySQL dev password: dev

## PHP Versions
Default PHP version is `7.0` but you can switch the PHP version by prefix you subdomain:
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
Redis is running on exposed port 6379

## Additional Setup
At the moment you need some manual setup:

### /etc/hosts entries

Add the following emtries to `/etc/hosts`

```
0.0.0.0 test.local.typo3.org
0.0.0.0 php56.test.local.typo3.org
0.0.0.0 php70.test.local.typo3.org
0.0.0.0 php71.test.local.typo3.org
```

### Create a folder
`~/work/test.local.typo3.org/`
