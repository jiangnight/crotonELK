# crotonELK


##FIRST


> download docker image logstash filebeat

```
docker pull willnight/crotonlogstash
docker pull willnight/crotonfilebeat
```

##second clone this project
```
git clone crotonELK
```

##start
```
start crotonlogstash：

docker run -ti --rm --network host -p 5044:5044  -v crotonELK/crotonlogstash/runconf/:/usr/share/logstash/runconf -v crotonELK/crotonlogstash/patterns/:/usr/share/logstash/patterns willnight/crotonlogstash ./bin/logstash -f ./runconf/scrapy.conf --config.reload.automatic

start crotonfilebeat:

docker run -ti --network host -v mygit/crotonELK/crotonfilebeat/filebeatconf/:/filebeatconf -v mygit/crotonELK/crotonfilebeat/scrapylog/:/scrapylog willnight/crotonfilebeat filebeat -e -c /filebeatconf/scrapy.yml -d "publish"
```
