## kafka-producer-perf-test.sh

kafka 프로듀서 퍼포먼스 측정

```
bin/kafka-producer-perf-test.sh \ 
--producer-props bootstrap.servers=my-kafka:9092 \ 
--topic hello.kafka \  
--num-records 10 \  
--throughput 1 \ 
--record-size 100 \ 
--preint-metric

```

```
bin/kafka-producer-perf-test.sh --producer-props bootstrap.servers=my-kafka:9092 --topic hello.kafka --num-records 10 --throughput 1 --record-size 100 --print-metric
```

kafka 컨슈머 퍼포먼스 측정

```
bin/kafka-consumer-perf-test.sh \ 
--bootstrap-server my-kafka:9092 \ 
--topic hello.kafka \ 
--messages 10 \ 
--show-detailed-stat
```

```
bin/kafka-consumer-perf-test.sh --bootstrap-server my-kafka:9092 --topic hello.kafka --messages 10 --show-detailed-stats
```

