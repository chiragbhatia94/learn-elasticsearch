# Shakespeare dataset

## Download
```bash
wget http://media.sundog-soft.com/es7/shakes-mapping.json
curl -O https://download.elastic.co/demos/kibana/gettingstarted/7.x/shakespeare.json
```

## Adding mapping to elasticsearch
```bash
curl -H "Content-Type: application/json" -XPUT 127.0.0.1:9200/shakespeare --data-binary @shakes-mapping.json
```

## Adding data to elasticsearch
```bash
curl -H "Content-Type: application/json" -XPOST '127.0.0.1:9200/shakespeare/_bulk' --data-binary @shakespeare.json
```

## Searching for text
```bash
curl -H "Content-Type: application/json" -XGET '127.0.0.1:9200/shakespeare/_search?pretty' -d '
{
    "query": {
        "match_phrase": {
            "text_entry": "to be or not to be" 
        }
    }
}'
```