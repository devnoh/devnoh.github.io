# Elasticsearch

## Install

$ brew install elasticsearch
$ brew services start elasticsearch

http://localhost:9200/

Sample: shakes-mapping.json
```
{
	"mappings" : {
 		"doc" : {
			"properties" : {
				"speaker" : {"type": "keyword" },
				"play_name" : {"type": "keyword" },
				"line_id" : { "type" : "integer" },
				"speech_number" : { "type" : "integer" }
			}
		}
	}
}
```