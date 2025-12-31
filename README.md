# Kafka

### Intro

1. 새 프로젝트 생성
   1. group, artifact: com.back.kafka
   2. name: kafka
   3. jdk, java: 25
   4. type: Gradle-Kotlin
   5. spring boot 4.0.1
2. 의존성 5개 추가
    ``` plain text
    Spring Boot Devtools
    Spring Web
    Lombok
    Spring for Apache Kafka
    Spring for Apache Kafka Streams
    ```
3. Kafka는 보통은 docker에 띄운다
   - 다만 개발, 테스트 환경에서는 임베디드 모드로 사용이 가능하다
   - `testImplementation("org.springframework.boot:spring-boot-starter-kafka-test")`
4. 스프링 이벤트 방식을 kafka로 전환하는 것이 수업 목표
5. 사용의 이점: 로깅, 이벤트 실패 시 안전장치의 역할을 하기도 함

---
### 용어 정리

- 토픽 : 레코드들이 저장되는 별도의 저장소(MySQL의 테이블과 유사)
- 레코드 : 카프카에서는 이벤트 = 레코드
- 프로듀서 : 이벤트를 생성하는 주체(`eventPublisher.publishEvent(...)`)
- 컨슈머 : 이벤트를 수신하는 주체(`@KafkaListener(topics = "MemberJoinedEvent")`)