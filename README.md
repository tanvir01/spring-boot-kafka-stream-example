# spring-boot-kafka-stream-example

# Instructions

1. Bring up the kafka (Confluent Image):

docker-compose up

2. Create the topics (input-topic & output-topic):

docker exec thebroker \                    
kafka-topics --bootstrap-server thebroker:9092 \          
             --create \                    
             --topic input-topic 

docker exec thebroker \
kafka-topics --bootstrap-server thebroker:9092 \
             --create \
             --topic output-topic

3. RUN the app

4. Create a console kafka consumer (To check the message transformations in output-topic)

docker exec --interactive --tty thebroker \
kafka-console-consumer --bootstrap-server thebroker:9092 \
                       --topic output-topic \ 
                       --from-beginning

5. Create a console kafka producer (To push messages in input-topic)

docker exec --interactive --tty thebroker \
kafka-console-producer --bootstrap-server thebroker:9092 \
                       --topic input-topic 
