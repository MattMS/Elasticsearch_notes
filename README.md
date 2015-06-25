# Learn Elasticsearch

Learn how to use Elasticsearch.


## Disclaimer

These notes have been created while I am learning Elasticsearch.
They will probably change as I learn more.
This is *not* a tutorial by an Elasticsearch expert.

You have been warned!


## Index (add) a document

```
PUT /my_index/my_document_type/1
{
	"email": "matt@example.com",
	"name": "Matt"
}
```

- [Indexing Employee Documents in Main Guide](https://www.elastic.co/guide/en/elasticsearch/guide/current/_indexing_employee_documents.html)


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

Exclude the document metadata:

```
GET /my_index/my_document_type/1/_source
```

Only get specific fields (with metadata):

```
GET /my_index/my_document_type/1?_source=link,title
```

- [Retrieving a Document (1) in Main Guide](https://www.elastic.co/guide/en/elasticsearch/guide/current/_retrieving_a_document.html)

- [Retrieving a Document (2) in Main Guide](https://www.elastic.co/guide/en/elasticsearch/guide/current/get-doc.html)


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
