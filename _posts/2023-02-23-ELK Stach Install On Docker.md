# ELK Stach Install On Docker

ELK 스택은 ElasticSearch Logstash Kibana 로 구성되어있음



### 1. ElasticSearch Download and run 

```bash
docker pull elasticsearch:8.6.2
docker network create elk
docker run -d --name elasticsearch --net elk -p 39200:9200 -p 39300:9300 -e ES_JAVA_OPTS="-Xms256m -Xmx256m" -e "discovery.type=single-node" -e "ELASTIC_PASSWORD=my_own_password" elasticsearch:8.6.2
```

(ES_JAVA_OPT 메모리를 설정하지 않을경우 ERROR: Elasticsearch exited unexpectedly 요론 애러가 뜬다.)

### 2. Logstash Download and run

```
docker pull logstash:8.6.2
docker run -d -p 38080:8080 -v /mnt/d/workspace/ELK:/local_dir --net elk -e ES_JAVA_OPTS="-Xms256m -Xmx256m"  --name logstash logstash:8.6.2

docker run -d -p 38080:8080 -v /mnt/d/workspace/settings:/usr/share/logstash/config -v /mnt/d/workspace/ELK:/local_dir --net elk -e ES_JAVA_OPTS="-Xms256m -Xmx256m"  --name logstash logstash:8.6.2

```



### 3. kibana

```
docker pull kibana:8.6.2
docker run -d --name kibana --net elk -p 35601:5601 kibana:8.6.2

```

