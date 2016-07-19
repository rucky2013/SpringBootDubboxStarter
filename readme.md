# Spring Boot Dubbox 集成组件

### 使用方法
在对应的生产者和消费者的pom.xml中引入下面的依赖
```xml
<dependency>
    <groupId>com.bluemoon</groupId>
    <artifactId>dubbox-spring-boot-starter</artifactId>
    <version>1.0-SNAPSHOT</version>
</dependency>
```

### 应用需做如下配置

生产者:
```yaml
spring.dubbo:
  application:
    name: provider-test #应用名
  registry:
    address: zookeeper://127.0.0.1:2181 #zk地址
  protocol:
    name: dubbo #协议名
    port: 20880 #协议端口
  scan: com.bluemoon.kafka.dubbo #扫描包名
```

消费者
```yaml
spring.dubbo:
  application:
    name: consumer-test
  registry:
    address: zookeeper://127.0.0.1:2181
  scan: com.bluemoon.kafka.dubbo
```