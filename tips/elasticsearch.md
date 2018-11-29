# Elasticsearch

## Install

```
$ brew install elasticsearch
$ brew services start elasticsearch
```

http://localhost:9200/

## Samples
```
http://media.sundog-soft.com/es6/shakes-mapping.json
http://media.sundog-soft.com/es6/shakespeare_6.0.json
```

$ http PUT localhost:9200/shakespeare < shakes-mapping.json
```
HTTP/1.1 200 OK
Warning: 299 Elasticsearch-6.5.1-8c58350 "the default number of shards will change from [5] to [1] in 7.0.0; if you wish to continue using the default of [5] shards, you must manage this on the create index request or with an index template" "Wed, 28 Nov 2018 19:02:45 GMT"
content-encoding: gzip
content-length: 76
content-type: application/json; charset=UTF-8

{
    "acknowledged": true,
    "index": "shakespeare",
    "shards_acknowledged": true
}
```

$ http POST localhost:9200/shakespeare/doc/_bulk?pretty < shakespeare_6.0.json
```
...
```

http://localhost:9200/shakespeare/_search?pretty

```
$ curl -H "Content-Type: application/json" -XGET '127.0.0.1:9200/shakespeare/_search?pretty' -d '
{
  "query":{
    "match_phrase": {
      "text_entry": "to be or not to be"
    }
  }
}'
```

## The Elastic Stack

* Elasticsearch
* Kibana
* Logstash / Beats
* X-Pack
