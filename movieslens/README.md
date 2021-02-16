# Movielens dataset

## Download
Download from grouplens.org

## Adding mapping to elasticsearch
```bash
curl -H "Content-Type: application/json" -XPUT 127.0.0.1:9200/movies -d '
{
    "mappings": {
        "properties": {
            "year": {
                "type": "date"
            }
        }
    }
}'
```

## Adding data to elasticsearch
```bash
curl -H "Content-Type: application/json" -XPOST '127.0.0.1:9200/movies/_doc/109487' -d '
{
    "genre": ["IMAX", "SCI-FI"],
    "title": "Interstellar",
    "year": 2014
}'
```

## Searching for text
```bash
curl -H "Content-Type: application/json" -XGET '127.0.0.1:9200/movies/_search?pretty'
```
