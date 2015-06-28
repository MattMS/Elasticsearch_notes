# Starting in Docker

There is an
[official repo for Elasticsearch](https://registry.hub.docker.com/_/elasticsearch/)
on Docker Hub Registry.

First pull the repo:

```
docker pull elasticsearch
```

Then start the container from the image:

```
docker run -d -p 9200:9200 elasticsearch
```

This will start the container in detched mode (`-d`), so you will return
to the command line.
It will also expose Elasticsearch on port `9200`.

If using Boot2Docker, get the IP with `boot2docker ip`.
