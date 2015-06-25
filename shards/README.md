# Shards

```
PUT /my_index
{
	"settings": {
		"number_of_replicas": 1,
		"number_of_shards": 3
	}
}
```

Creates an index with 3 primary shards with 3 replicas (1 each).

The number of shards is fixed at the creation of the index.
Replicas can be changed later.

```
PUT /my_index/_settings
{
	"number_of_replicas": 2
}
```

- [Add an Index in Main Guide](https://www.elastic.co/guide/en/elasticsearch/guide/current/_add_an_index.html)

- [Scale Horizontally in Main Guide](https://www.elastic.co/guide/en/elasticsearch/guide/current/_scale_horizontally.html)
