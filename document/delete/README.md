# Delete a document

```
DELETE /my_index/my_document_type/123
```

Returns:

```
{
	"_id": "123",
	"_index": "my_index",
	"_type": "my_document_type",
	"_version": 1,
	"found": true
}
```

- [Deleting a Document in Main Guide](https://www.elastic.co/guide/en/elasticsearch/guide/current/delete-doc.html)


## Delete all documents

Delete all documents in index of the given type:

```
DELETE /my_index/my_document_type/
```
