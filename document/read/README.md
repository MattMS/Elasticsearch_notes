# Retrieve a document

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


## Links

- [Retrieving a Document (1) in Main Guide](https://www.elastic.co/guide/en/elasticsearch/guide/current/_retrieving_a_document.html)

- [Retrieving a Document (2) in Main Guide](https://www.elastic.co/guide/en/elasticsearch/guide/current/get-doc.html)
