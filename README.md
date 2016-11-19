# Docker DevBox

run `docker-compose up`

## What is included?
- PHP 5.6
- PHP 7.0
- PHP 7.1
- MySQL (latest)

## Database
You can connect to the MySQL database with the hostname `mysql` on port `3306`

## PHP Versions
Default PHP version is `7.0` but you can switch the PHP version by prefix you subdomain:
Examples:
- http://test.local.typo3.org [PHP 7.0]
- http://php56.test.local.typo3.org [PHP 5.6]
- http://php70.test.local.typo3.org [PHP 7.0]
- http://php71.test.local.typo3.org [PHP 7.1]

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
`~/work/vagrant/vHosts/test.local.typo3.org/`
