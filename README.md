# Elasticsearch

## Docker setup
```bash
docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" --name elasticsearch -d docker.elastic.co/elasticsearch/elasticsearch:7.10.1 
```
