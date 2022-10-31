From https://github.com/deviantony/docker-elk


https://www.robertobandini.it/2021/02/07/how-to-run-filebeat-with-docker-and-use-it-with-elk-stack/


docker exec -u root -it docker-elk-stack-logstash-1 bash

logstash -f /usr/share/logstash/pipeline/sample.conf --config.reload.automatic


cat /usr/share/logstash/log_data/inlog.log | nc -q0 localhost 50000

cat /usr/share/logstash/log_data/inlog.log | nc -c localhost 50000

cat inlog.log | nc -q0 localhost 50000

curl -XGET 'localhost:9600/?pretty'

docker service logs -f elk_logstash

docker logs -f docker-elk-stack-logstash-1

docker logs -f 031de23cb352



docker-compose up -d logstash kibana

docker-compose restart logstash kibana

https://github.com/deviantony/docker-elk/issues/622
http://localhost:9600/_node/pipelines/main/?pretty

curl -s -D- http://localhost:9600/_node/pipelines/main\?pretty

docker-compose down -v

curl -XGET http://localhost:9200 -u elastic:changeme


# Changes made from original repo
- Added pipeline
- Added UDP and TCP pipeline items and tested
- Removed xpack trialed and fixed the authorization part.