# Cluster

```
GET /_cluster/health
```

Returns:

```
{
"active_primary_shards": 0,
"active_shards": 0,
"cluster_name": "elasticsearch",
"initializing_shards": 0,
"number_of_data_nodes": 1,
"number_of_nodes": 1,
"relocating_shards": 0,
"status": "green",
"timed_out": false,
"unassigned_shards": 0
}
```


## Status levels

green
: All primary and replica shards are active.

yellow
: All primary shards are active, but not all replica shards are active.

red
: Not all primary shards are active.


## Links

- [Cluster Health in Main Guide](https://www.elastic.co/guide/en/elasticsearch/guide/current/cluster-health.html)
