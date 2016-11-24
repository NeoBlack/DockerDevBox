FROM nginx:latest

MAINTAINER Frank Nägler <frank.naegler@typo3.com>

COPY ./devbox.21r.de.conf /etc/nginx/conf.d/devbox.21r.de.conf
COPY ./elastic.devbox.21r.de.conf /etc/nginx/conf.d/elastic.devbox.21r.de.conf
COPY ./mail.devbox.21r.de.conf /etc/nginx/conf.d/mail.devbox.21r.de.conf

# Install mysql client
RUN apt-get update && \
   apt-get install -y graphicsmagick &&\
   apt-get install -y mysql-client && \
   apt-get install -y ssh && \
   apt-get install -y rsync