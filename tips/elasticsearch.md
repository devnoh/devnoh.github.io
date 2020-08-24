# Elasticsearch

## Install

Using Homebrew:
```
$ brew install elasticsearch
$ brew services start elasticsearch
$ brew services stop elasticsearch
```

```
$ brew install elasticsearch@5.6
$ brew services start elasticsearch@5.6
$ brew services stop elasticsearch@5.6
```

Using Docker:
```
$ docker run -d --name elasticsearch -p 9200:9200 -p 9300:9300 -e “discovery.type=single-node” elasticsearch:5
```

http://localhost:9200/

* List All Indices
http://localhost:9200/_cat/indices

## Samples
```
$ wget http://media.sundog-soft.com/es6/shakes-mapping.json
$ wget http://media.sundog-soft.com/es6/shakespeare_6.0.json
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


## Sample Queries

POST https://localhost:9200/inventory/_search
POST https://localhost:9200/inventory/_delete_by_query

{
  "query": {
    "bool": {
      "must": [
        {
          "match": {
            "type": "XYZ"
          }
        }
      ]
    }
  }
}



## Others

https://www.elastic.co/guide/en/kibana/current/tutorial-build-dashboard.html


```
curl -O https://download.elastic.co/demos/kibana/gettingstarted/8.x/shakespeare.json

curl -X PUT "localhost:9200/shakespeare?pretty" -H 'Content-Type: application/json' -d'
{
  "mappings": {
    "properties": {
    "speaker": {"type": "keyword"},
    "play_name": {"type": "keyword"},
    "line_id": {"type": "integer"},
    "speech_number": {"type": "integer"}
    }
  }
}
'

curl -u elastic -H 'Content-Type: application/x-ndjson' -XPOST 'localhost:9200/shakespeare/_bulk?pretty' --data-binary @shakespeare.json


http://localhost:9200/_cat/indices?v&pretty
http://localhost:9200/shakespeare/_search?q=play_name:%22Henry%20IV%22

```