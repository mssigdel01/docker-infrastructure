Steps:
    - Edit `/etc/hosts` file to include Map from IP to docker (example: 10.10.4.123  docker.for.mac.host.internal)
    - docker-compose up -d (To start the container)
    - docker-compose down (To stop the container)
Services:
    - Confluent kafka
    - ElasticSearch
    - Redis
Validation:
    - `./validate.sh` [Kafka validation]
    - `brew install redis-cli`[One time], `redis-cli ping` (expect PONG as output) [Redis Validation]
    - `curl http://localhost:9200` [Elastic search validation]

