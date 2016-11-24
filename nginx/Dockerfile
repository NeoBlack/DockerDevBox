FROM nginx:latest

MAINTAINER Frank Nägler <frank.naegler@typo3.com>

COPY ./local.typo3.org.conf /etc/nginx/conf.d/local.typo3.org.conf
COPY ./elastic.local.typo3.org.conf /etc/nginx/conf.d/elastic.local.typo3.org.conf
COPY ./mail.local.typo3.org.conf /etc/nginx/conf.d/mail.local.typo3.org.conf

# Install mysql client
RUN apt-get update && \
   apt-get install -y graphicsmagick &&\
   apt-get install -y mysql-client && \
   apt-get install -y ssh && \
   apt-get install -y rsync