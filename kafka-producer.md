## Kafka 프로듀서

1. 프로듀서 실행

```
 bin/kafka-console-producer.sh --bootstrap-server my-kafka:9092  --topic hello.kafka
```

2. 키를 가지는 레코드 전송 (':' 으로 구분자 선언)

```
bin/kafka-console-producer.sh --bootstrap-server my-kafka:9092 \
 --topic hello.kafka \
 --property "parse.key=true" \
 --property "key.separator=:"
```

### 동일 키를 가지는 레코드는 토픽의 같은 파티션에 저장됨 키를 가지지 않는다면 라운드로빈으로 파티션에 저장됨
