## Kafka 실행

1. 주키퍼 실행

```bash
bin/zookeeper-server-start.sh config/zookeeper.properties
```

2. 브로커 실행(kafka 서버는 broker로 이해하면됨)

```
bin/kafka-server-start.sh config/server.properties
```

3. 카프카 정상 실행 여부 확인 

```
bin/kafka-broker-api-versions.sh --bootstrap-server localhost:9092
```

3-1. 카프카토픽의 목록 확인(실행여부 확인)

```
bin/kafka-topics.sh --bootstrap-server localhost:9092 --list
```

4. 테스트 편의를 위한 host 설정

``` 
sudo vi /etc/hosts
127.0.0.1 my-kafka // 추가
```

5. 토픽생성

```
bin/kafka-topics.sh --create \ 
--bootstrap-server my-kafka:9092 \ 
--topic ${카프카이름}
```

5-1. describe 옵션(상태정보확인 파티션 개수, 레플리카 개수, config 등)

```
bin/kafka-topics.sh --create \ 
--bootstrap-server my-kafka:9092 \ 
--topic ${카프카이름} --describe
```

5-2. 파티션 개수, 복제 개수, 토픽 데이터 유지기간 등 실행

```
bin/kafka-topics.sh --create \ 
--bootstrap-server my-kafka:9092 \ 
--topic ${카프카이름} \
--partitions ${파티션개수} \
--replication-factor 1 \
--config retention.ms=172800000
```

5-3 alter 파티션 개수 변경

```
bin/kafka-topics.sh --create \ 
--bootstrap-server my-kafka:9092 \ 
--topic ${카프카이름} \
--alter \
--partitions ${파티션개수}
```

```
bin/kafka-topics.sh --bootstrap-server my-kafka:9092 --topic test --alter --partitions 4
```

6. 토픽삭제

```
bin/kafka-topics.sh --bootstrap-server my-kafka:9092 --topic ${토픽이름} --delete
```

   
