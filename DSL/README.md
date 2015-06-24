# Query with Domain-Specific Language (DSL)

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

Match people over 24 with a name containing "Matt":

```
GET /my_index/my_document_type/_search
{
	"query": {
		"filtered": {
			"filter": {
				"range": {
					"age": {
						"gt": 24
					}
				}
			},
			"query": {
				"match": {
					"name": "Matt"
				}
			}
		}
	}
}
```

A `query.match` of "rock climbing" will also match "rock music" but with
a lower score.
The `hits` array is ordered by descending scores.

Use `query.match_phrase` to require finding the exact text in the field.

- [Full-Text Search](https://www.elastic.co/guide/en/elasticsearch/guide/current/_full_text_search.html)

- [More-Complicated Searches](https://www.elastic.co/guide/en/elasticsearch/guide/current/_more_complicated_searches.html)

- [Phrase Search](https://www.elastic.co/guide/en/elasticsearch/guide/current/_phrase_search.html)

- [Search with Query DSL](https://www.elastic.co/guide/en/elasticsearch/guide/current/_search_with_query_dsl.html)
