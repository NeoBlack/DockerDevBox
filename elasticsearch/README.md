## Info

This container builds on the official elasticsearch image. Currently installing elasticsearch 2.2.1
Available at [ddogs/elasticsearch](https://registry.hub.docker.com/u/ddogs/elasticsearch/)

## Use

```
docker run ddogs/elasticsearch
```

Optionally you can override specific elasticsearch configuration settings:

```
docker run ddogs/elasticsearch -Des.node.name="awesome_node"
```


Example docker-compose file:

```
elasticsearch:
  image: ddogs/elasticsearch
  hostname: elasticsearch
  privileged: true
  volumes:
    - ./storage:/usr/share/elasticsearch/data
    - ./config:/usr/share/elasticsearch/config
  ports:
    - "9200:9200/tcp"
    - "9300:9300/tcp"
```

As seen above, you can map specific volumes for your _data_ directory and your own elasticsearch config YML file.

__NOTE__: privileged mode is required, because of performance optimizations (memlock unlimited). (Source:  [Hewlett-Packard-ESS/docker-elasticsearch](https://github.com/Hewlett-Packard-ESS/docker-elasticsearch)

## Cluster
To start an elasticsearch cluster, you can use the cluster.yml file for docker-compose.
It starts 3 elasticsearch data nodes and one client node. The ports 9200 and 9300 of the client-node are exposed.

## Plugins
The following elasticsearch plugins are installed in the image:
- [head](http://mobz.github.io/elasticsearch-head/)
- [kopf](https://github.com/lmenezes/elasticsearch-kopf)
- [delete-by-query](https://github.com/elastic/elasticsearch/blob/master/docs/plugins/delete-by-query.asciidoc)

## Logging
By default, only WARN and above will be visible in the stdout and subsequently docker logs.  INFO and above are logged to /storage/logs

## License
This docker application is distributed unter the MIT License (MIT).

Elasticsearch itself is licensed under the [Apache](https://github.com/elastic/elasticsearch/blob/master/LICENSE.txt) License.
