Steps:

    - Edit `/etc/hosts` file to include Map from IP address to docker (example: 7.7.7.123  docker.for.mac.host.internal)
    
    - Change password for mysql
    
    - Check if the local path for mysql exists and docker has permission
    
    - docker-compose up -d (To start the container)
    
    - docker-compose up -d {{list of service_name separated by white space}} (To start only those services and its dependencies in the container)
        - Example: docker-compose up -d redis mysql kadmin
        
    - docker-compose down (To stop the container)
    
Services: (With their exposed port)

    - Confluent kafka
        - Zookeeper : 2181
        - Kafka : 9092
        - Schema Registry : 8081
        - Rest Kafka : 9080
    
    - ElasticSearchdoc
        - Transport Client : 9200
        - Rest Client : 9300
    
    - Redis : 6379
    
    - Pubsub Emulator : 8085
    
    - Bigtable Emulator : 9035
    
    - Kadmin : 7080 (http://localhost:7080/kadmin/)
    
    - mysql : 3306
    
    
Validation:

    - `./validate.sh` [Kafka validation]
    
    - `brew install redis-cli`[One time], `redis-cli ping` (expect PONG as output) [Redis Validation]
    
    - `curl http://localhost:9200` [Elastic search validation]
    
    - `curl http://localhost:7080/kadmin/` [Kadmin validation]
    
    - `nc -z localhost 3306` [MySQL validation]
    
    - `curl http://localhost:9000` [Kadmin validation]
