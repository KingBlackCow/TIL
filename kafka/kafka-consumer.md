## kafka-console-consumer.sh

```
 bin/kafka-console-consumer.sh --bootstrap-server my-kafka:9092 \
--topic test \
--property print.key=true \
--property key.seperato="-" \
--from-beginning
```

옵션 

--max-messages : 최대 컨슘 메시지 개수

```
 bin/kafka-console-consumer.sh --bootstrap-server my-kafka:9092 \
--topic test \
--from-beginning
--max-messages 1
```

--partition: 특정 파티션만 컨슘

```
 bin/kafka-console-consumer.sh --bootstrap-server my-kafka:9092 \
--topic test \
--partition 2 \
--from-beginning \

```

--group: 컨슈머 그룹을 기반으로 kafka-console-consumer가 동작함, 컨슈머 그룹으로 토픽의 레코드를 가져갈 경우 어느 레코드까지 읽었는지에 대한 데이터가 카프카 브로커에 저장된다.

![image-20230705015502306](/Users/admin/Library/Application Support/typora-user-images/image-20230705015502306.png)

```
 bin/kafka-console-consumer.sh --bootstrap-server my-kafka:9092 \
--topic hello.kafka \
--group hello-group \
--from-beginning
```

컨슈머 그룹 내 메시지 소비

```
 bin/kafka-console-consumer.sh --bootstrap-server my-kafka:9092 \
--topic hello.kafka \
--group hello-group
```

--group 옵션사용 시 **__consumer_offsets** 이라는 토픽이 새로 만들어지며 어디까지 consumer가 소비했는지 저장된다.



## kafka-consumer-groups.sh

현재 컨슈머 그룹 확인

```
bin/kafka-consumer-groups.sh --bootstrap-server my-kafka:9092 --list
```

컨슈머 그룹 정보확인

```
bin/kafka-consumer-groups.sh --bootstrap-server my-kafka:9092 --group ${컨슈머 그룹 이름} --describe
```

오프셋 리셋: 어느 오프셋 부터 정보를 가져와야할지 확인 

```
bin/kafka-consumer-groups.sh --bootstrap-server my-kafka:9092 --group hello-group --topic ${토픽이름} --reset-offsets --to-earliest --execute
```

bin/kafka-consumer-groups.sh --bootstrap-server my-kafka:9092 --group hello-group --topic hello.kafka --reset-offsets --to-earliest --execute



