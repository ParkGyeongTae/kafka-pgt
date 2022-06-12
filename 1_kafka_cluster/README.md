# kafka-pgt

## 토픽 조회
- kafka-topics --list --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094

## 토픽 만들기
- kafka-topics --create --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --replication-factor 1 --partitions 1 --topic mytopic