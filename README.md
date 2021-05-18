# Lv2_MSA_ETC

***cd 카프카설치 경로/bin/windows
zookeeper-server-start.bat ../../config/zookeeper.properties
kafka-server-start.bat ../../config/server.properties

- zookeeper 
cd 카프카설치 경로/bin/windows
zookeeper-server-start.bat ../../config/zookeeper.properties	

-kafka
cd 카프카설치 경로/bin/windows
kafka-server-start.bat ../../config/server.properties

## Kafka 설치
1. 주키퍼 실행  
   
   ./zookeeper-server-start.sh ../config/zookeeper.properties &
   
2. 카프카 broker 실행  
   
   ./kafka-server-start.sh ../config/server.properties
   
( 3 ~ 4 는 건너뛰어도 됨 )
3. 카프카 topic 만들기  

   ./kafka-topic.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic teamtwohotel
   
4. 카프카 producer 실행  
 
   ./kafka-console-poducer.sh --broker-list localhost:9092 --topic teamtwohotel
    
5. 카프카 consumer 실행  
 
 ./kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic teamtwohotel --from-beginning
    
6. 카프카 토픽 삭제
 
 ./kafka-topics.sh --zookeeper localhost:2181 --delete --topic DummyTopic
 
7. 카프카 토픽 리스트

 ./kafka-topics.sh --list --zookeeper localhost:2181
 
8. 카프카가 비정상일 때 
  sudo lsof -i :2181 한뒤  
  kill -9 pid 하고 다시 띄워준다

## Kafka Topic 

1.1) Topic 생성
  - /usr/local/kafka/bin/kafka-topics.sh --bootstrap-server http://localhost:9092 --topic topic_example --create --partitions 1 --replication-factor 1
