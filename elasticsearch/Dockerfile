# inspired by https://github.com/the-diamond-dogs-group-oss/docker-elasticsearch
# extended by another plugin
FROM elasticsearch:2.3

MAINTAINER Frank Nägler <frank.naegler@typo3.com>

# Performance Tweaks
RUN echo "* - nofile 65535" >> /etc/security/limits.conf && \
    echo "* - memlock unlimited" >> /etc/security/limits.conf && \
    echo vm.max_map_count=262144 > /etc/sysctl.d/max_map_count.conf && \
    echo vm.swappiness=0 > /etc/sysctl.d/swappiness.conf

ENV ES_HEAP_SIZE 1g
ENV MAX_OPEN_FILES=65535
ENV MAX_LOCKED_MEMORY=unlimited

# optional volumes for data and config directory
VOLUME /usr/share/elasticsearch/data
VOLUME /usr/share/elasticsearch/config

# install ES plugins (marvel, kopf, head)
RUN /usr/share/elasticsearch/bin/plugin install mobz/elasticsearch-head/latest && \
    /usr/share/elasticsearch/bin/plugin install lmenezes/elasticsearch-kopf/latest && \
    /usr/share/elasticsearch/bin/plugin install delete-by-query &&\
    /usr/share/elasticsearch/bin/plugin install analysis-stempel

CMD ["elasticsearch"]
