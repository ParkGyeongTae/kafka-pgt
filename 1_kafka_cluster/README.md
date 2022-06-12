# kafka-pgt

## 토픽 조회
- kafka-topics --list --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094

## 토픽 만들기
- kafka-topics --create --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --replication-factor 1 --partitions 1 --topic mytopic-1-1
- kafka-topics --create --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --replication-factor 2 --partitions 2 --topic mytopic-2-2
- kafka-topics --create --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --replication-factor 3 --partitions 3 --topic mytopic-3-3

## 토픽 지우기
- kafka-topics --delete --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --topic mytopic,topic-kafka-1,topic-kafka-2,topic-kafka-3

## 토픽 상세보기
- kafka-topics --describe --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --topic mytopic