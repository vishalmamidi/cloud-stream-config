# cloud-stream-config

#application properties dlq retrys 

````
spring.cloud.stream.kafka.binder.brokers=amazonaws.com:9092,amazonaws.com:9092
spring.cloud.stream.kafka.binder.autoCreateTopics= false
#Kafka consumers
spring.cloud.function.definition=offBoardWalletConsumer
#offBoardWalletConsumer
spring.cloud.stream.bindings.offBoardWalletConsumer-in-0.destination=jb-client-offboard
spring.cloud.stream.bindings.offBoardWalletConsumer-in-0.group=amazon.msk.canary.group.broker-1
spring.cloud.stream.bindings.offBoardWalletConsumer-in-0.consumer.maxAttempts= 3
spring.cloud.stream.kafka.bindings.offBoardWalletConsumer-in-0.consumer.enableDlq= true
spring.cloud.stream.kafka.bindings.offBoardWalletConsumer-in-0.consumer.dlqName= jb-client-offboard-dlq
#supressLogs
logging.level.org.apache.kafka.clients.consumer.internals.ConsumerCoordinator=warn
logging.level.org.apache.kafka.clients.consumer.internals.SubscriptionState=warn
logging.level.org.springframework.cloud.stream.binder.kafka=warn
logging.level.org.apache.kafka.clients.consumer.internals.AbstractCoordinator=warn
```
