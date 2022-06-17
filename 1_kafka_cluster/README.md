# kafka-pgt

# 토픽
## 토픽 조회
- kafka-topics --list --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094

## 토픽 만들기
- kafka-topics --create --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --replication-factor 1 --partitions 1 --topic mytopic-1-1
- kafka-topics --create --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --replication-factor 2 --partitions 2 --topic mytopic-2-2
- kafka-topics --create --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --replication-factor 3 --partitions 3 --topic mytopic-3-3
- kafka-topics --create --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --replication-factor 3 --partitions 30 --topic mytopic-3-30

## 토픽 지우기
- kafka-topics --delete --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --topic mytopic-1-1,mytopic-2-2,mytopic-3-3

## 토픽 상세보기
- kafka-topics --describe --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --topic mytopic-1-1
- kafka-topics --describe --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --topic mytopic-2-2
- kafka-topics --describe --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --topic mytopic-3-3



# 메세지

## 메세지 쓰기
- kafka-console-producer --broker-list kafka-1:9092,kafka-2:9093,kafka-3:9094 --topic mytopic-1-1
- kafka-console-producer --broker-list kafka-1:9092,kafka-2:9093,kafka-3:9094 --topic mytopic-2-2
- kafka-console-producer --broker-list kafka-1:9092,kafka-2:9093,kafka-3:9094 --topic mytopic-3-3 --property "parse.key=true" --property "key.separator=:"


## 메세지 읽기
- kafka-console-consumer --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --topic mytopic-1-1 --from-beginning
- kafka-console-consumer --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --topic mytopic-2-2 --from-beginning
- kafka-console-consumer --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --topic mytopic-3-3 --from-beginning --property print.key=true --property key.separator="-"
- kafka-console-consumer --bootstrap-server kafka-1:9092 --topic mytopic-3-3 --from-beginning
- kafka-console-consumer --bootstrap-server kafka-2:9093 --topic mytopic-3-3 --from-beginning
- kafka-console-consumer --bootstrap-server kafka-3:9094 --topic mytopic-3-3 --from-beginning


# 컨슈머 그룹

## 컨슈머 그룹 리스트
- kafka-consumer-groups --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --list


## 컨슈머 그룹 상세보기
- kafka-consumer-groups --bootstrap-server kafka-1:9092,kafka-2:9093,kafka-3:9094 --group console-consumer-66325 --describe