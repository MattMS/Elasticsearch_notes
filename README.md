# Learn Elasticsearch

Learn how to use Elasticsearch.


## Disclaimer

These notes have been created while I am learning Elasticsearch.
They will probably change as I learn more.
This is *not* a tutorial by an Elasticsearch expert.

You have been warned!


## Starting in Docker

There is an [official repo for Elasticsearch](https://registry.hub.docker.com/_/elasticsearch/).

First pull the repo:

```
docker pull elasticsearch
```

Then start the container from the image:

```
docker run -d -p 9200:9200 elasticsearch
```

This will start the container in detched mode (-d), so you will return
to the command line.
It will also expose Elasticsearch on port 9200 on the Docker IP.


## Index (add) a document

```
PUT /my_index/my_document_type/1
{
	"email": "matt@example.com",
	"name": "Matt"
}
```

- https://www.elastic.co/guide/en/elasticsearch/guide/current/_indexing_employee_documents.html


## Retrieve a document

```
GET /my_index/my_document_type/1
```

Returns:

```
{
	"_id": "1",
	"_index": "my_index",
	"_source": {
		"email": "matt@example.com",
		"name": "Matt"
	},
	"_type": "my_document_type",
	"_version": 1,
	"found": true
}
```

- https://www.elastic.co/guide/en/elasticsearch/guide/current/_retrieving_a_document.html


## Search

```
GET /my_index/my_document_type/_search
```

Returns:

```
{
	"_shards": {},
	"hits": {
		"hits": [
			{
				"_id": "1",
				"_index": "my_index",
				"_score": 1,
				"_source": {
					"email": "matt@example.com",
					"name": "Matt"
				},
				"_type": "my_document_type",
				"_version": 1,
				"found": true
			}
		],
		"max_score": 1,
		"total": 1
	},
	"timed_out": false,
	"took": 6
}
```

```
GET /my_index/my_document_type/_search?q=email:matt
```

- https://www.elastic.co/guide/en/elasticsearch/guide/current/_search_lite.html


## Query Domain-Specific Language (DSL)

```
GET /my_index/my_document_type/_search
{
	"query": {
		"match": {
			"email": "matt@example.com"
		}
	}
}
```

- https://www.elastic.co/guide/en/elasticsearch/guide/current/_search_with_query_dsl.html
