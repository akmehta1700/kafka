docker run --rm -it --link kafka-broker --name temp kafka:3.1.0 bin/kafka-topics.sh --create --topic test-topic --bootstrap-server kafka-broker:9092
Created topic test-topic.

docker run --rm -it --link kafka-broker --name temp kafka:3.1.0 bin/kafka-topics.sh --list --topic test-topic --bootstrap-server kafka-broker:9092
test-topic

docker run --rm -it --link kafka-broker --name temp kafka:3.1.0 bin/kafka-topics.sh --list --bootstrap-server kafka-broker:9092
quickstart-events
test-topic


docker run --rm -it --link kafka-broker --name producer kafka:3.1.0 bin/kafka-console-producer.sh --bootstrap-server kafka-broker:9092 --topic quickstart-events

producer
docker run --rm -it --link kafka-broker --name producer kafka:3.1.0 bin/kafka-console-producer.sh --bootstrap-server kafka-broker:9092 --topic quickstart-events

>This is a test message
>this is a first message
>this is a second message
>this is a third message
>112233
>test message
>1122


consumer
docker run --rm -it --link kafka-broker --name consumer kafka:3.1.0 bin/kafka-console-consumer.sh --bootstrap-server kafka-broker:9092 --topic quickstart-events --from-beginning

This is a test message
this is a first message
this is a second message
this is a third message
This is a test message
this is a first message
this is a second message
this is a third message
112233
test message
1122
