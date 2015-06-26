# Learn Elasticsearch

Learn how to use Elasticsearch.

Example code is listed in alphabetical order, which is different to what
Elasticsearch will return.


## Disclaimer

These notes have been created while I am learning Elasticsearch.
They will probably change as I learn more.
This is *not* a tutorial by an Elasticsearch expert.

You have been warned!


## CRUD

[Create](./document/create),
[read](./document/read),
[update](./document/update) and
[delete](./document/delete) documents.


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
GET /my_index/my_document_type/_search?q=name:Matt
```

- [Search Lite](https://www.elastic.co/guide/en/elasticsearch/guide/current/_search_lite.html)
