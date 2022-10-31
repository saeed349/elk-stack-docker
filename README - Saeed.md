# SOURCE
https://github.com/deviantony/docker-elk

## Issues
### Pipeline
https://github.com/deviantony/docker-elk/issues/622
http://localhost:9600/_node/pipelines/main/?pretty

# For Bilebeats
https://www.robertobandini.it/2021/02/07/how-to-run-filebeat-with-docker-and-use-it-with-elk-stack/


# TCP Command
cat inlog.log | nc -q0 localhost 50000

# Bash into logstash 
## As root
docker exec -u root -it docker-elk-stack-logstash-1 bash

## For logs
docker logs -f docker-elk-stack-logstash-1

# To talk to Logstash

## Status
curl -XGET 'localhost:9600/?pretty'

## To see status of pipeline
curl -s -D- http://localhost:9600/_node/pipelines/udp_test\?pretty

## Elastic search login
curl -XGET http://localhost:9200 -u elastic:changeme

# Docker Commands

## Restart
docker-compose restart logstash kibana

## To remove volume
docker-compose down -v


# Changes made from original repo
- Added pipeline
- Added UDP and TCP pipeline items and tested
- Removed xpack trialed and fixed the authorization part.