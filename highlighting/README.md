# Highlighting matches in results

```
GET /my_index/my_document_type/_search
{
	"highlight": {
		"fields": {
			"about": {}
		}
	},
	"query": {
		"match_phrase": {
			"about": "rock climbing"
		}
	}
}
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
					"about": "I love to go rock climbing",
					"name": "Matt"
				},
				"_type": "my_document_type",
				"_version": 1,
				"found": true,
				"highlight": {
					"about": [
						"I love to go <em>rock</em> <em>climbing</em>"
					]
				}
			}
		],
		"max_score": 1,
		"total": 1
	},
	"timed_out": false,
	"took": 6
}
```

- [Highlighting Our Searches](https://www.elastic.co/guide/en/elasticsearch/guide/current/highlighting-intro.html)
