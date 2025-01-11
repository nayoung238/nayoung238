## 👋 실패 속에서 본질을 찾아내는 나영입니다

**불확실한 상황**에서 최적의 솔루션을 찾아가는 것을 좋아합니다.<br>
'**제대로 돌아가는**' 코드 작성을 좋아합니다.

<br>

## 📚 리소스 최적화 리스트, 근데 실패를 곁들인...

CI/CD 파이프라인 개선해 **4m 4s -> 1m 16s로 시간 단축**
- workflow에 [gradle 패키지 캐싱 단계](https://github.com/imzero238/cicd-test) 추가

<br>

[Bloom Filter로 DB I/O 최소화](https://medium.com/@im_zero/bloom-filter%EB%A1%9C-db-%EB%B6%80%ED%95%98-%EA%B0%90%EC%86%8C-%EC%84%B1%EB%8A%A5-61-%EA%B0%9C%EC%84%A0-e46e8ce62d6d)해 **성능 61% 개선**

- **154.15ms -> 59.17ms로 개선**
- Unique 제약 조건을 DB Layer가 아닌 Service Layer에서 확인

<br>

[Lua Script로 Redis 트랜잭션 구현]((https://medium.com/@im_zero/%EC%BF%A0%ED%8F%B0-%EB%B0%9C%EA%B8%89%EC%9D%84-%EC%9C%84%ED%95%9C-redis-streams-lua-script-%EC%A0%81%EC%9A%A9%EA%B8%B0-5f3dc4d02b2c))해 **81.9% 시간 단축**<br>
<img width="650" alt="lua_script_session_callback_performance_result" src="https://github.com/user-attachments/assets/d39daa5c-d13a-4e8a-9ecd-a39c716c757c" />
- SessionCallback 대신 Lua script 사용해 **2.73s -> 0.495s 개선**
- [Lua Script 코드](https://github.com/imzero238/Coupon-service/blob/main/src/main/java/com/ecommerce/couponservice/redis/manager/CouponStockRedisManager.java#L121)

<br>

[Kafka Streams 윈도우 집계로 DB I/O 최소화](https://medium.com/@im_zero/kafka-streams%EC%9D%98-window-results-%EC%BB%A8%ED%8A%B8%EB%A1%A4%ED%95%98%EA%B8%B0-3c20c360cf02), 그러나...😅

- **배치 단위로 쓰기 버퍼링 목표 달성** (사용 중인 MySQL, MongoDB 쓰기 버퍼링 기능에서 아이디어 획득)
- [Topology 코드](https://github.com/imzero238/Item-service/blob/master/src/main/java/com/ecommerce/itemservice/kafka/config/streams/StockAggregationTopology.java#L42)
- 그러나 Drop Event 처리를 위한 **Window + Grace 기간에 따른 버퍼링**이 메모리 문제로 이어져 적용 실패

<br>

[Kafka Stremas Join](https://medium.com/@im_zero/kstream-ktable-join-%EC%A0%81%EC%9A%A9-%EC%8B%A4%ED%8C%A8%EA%B8%B0-f7b8bfa11e42)으로 **DB I/O 50% 감소 & 처리 속도 83% 개선**, 그러나...😅

- **처리 속도 10.2s -> 1.7s 개선**
- [KStream-KTable Join 코드](https://github.com/imzero238/Order-service/blob/master/src/main/java/com/ecommerce/orderservice/kafka/config/streams/KStreamKTableJoinConfig.java#L83)
- 그러나 원천 데이터의 빠른 영속화 불가로 적용 실패

<br>

[Hibernate Query Plan Cache](https://medium.com/@im_zero/hibernate-query-plan-cache-oom-%EC%97%90%EB%9F%AC-%ED%95%B4%EA%B2%B0-298f3feae93a)활용해 OOM 에러 해결<br>
<img width="650" alt="in_clause_padding_performance_result" src="https://github.com/user-attachments/assets/d27b40dd-463f-4d27-b592-5aa056aece40" />
- IN 절 padding 설정으로 최대한 같은 SQL 구문 재사용 유도 (0.0041s -> 0.00385s)
- [@DynamicUpdate 대신 @Version 사용해 cached SQL 구문 사용](https://medium.com/@im_zero/version-vs-dynamicupdate-342d27dc59fd)

<br>

더 많은 경험을 [medium](https://medium.com/@im_zero)에서 공유 중... 💚

<br>

## 🛠️ Tech Stack

<div align="center">

### DEV

<img alt="Static Badge" src="https://img.shields.io/badge/java17-%23007396?style=for-the-badge&logo=java&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Spring%20Boot-%236DB33F?style=for-the-badge&logo=Spring%20Boot&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Spring Data JPA-%236DB33F?style=for-the-badge&logo=Spring&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Spring Cloud Gateway-%236DB33F?style=for-the-badge&logo=Spring&logoColor=white"><br>
<img alt="Static Badge" src="https://img.shields.io/badge/Apache%20Kafka-%23231F20?style=for-the-badge&logo=Apache%20Kafka&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Redis-%23FF4438?style=for-the-badge&logo=Redis&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Resilience 4J-%23231F20?style=for-the-badge&logoColor=white">


### DB

<img alt="Static Badge" src="https://img.shields.io/badge/MySQL-%234479A1?style=for-the-badge&logo=mysql&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/MongoDB-%2347A248?style=for-the-badge&logo=MongoDB&logoColor=white">

### Test & Monitoring

<img alt="Static Badge" src="https://img.shields.io/badge/JUnit 5-%2325A162?style=for-the-badge&logo=JUnit5&logoColor=white"><br><img alt="Static Badge" src="https://img.shields.io/badge/prometheus-%23E6522C?style=for-the-badge&logo=prometheus&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Grafana-%23F46800?style=for-the-badge&logo=Grafana&logoColor=white">

<br>

<a href="https://github.com/devxb/gitanimals">
<img
  src="https://render.gitanimals.org/farms/imzero238"
  width="600"
  height="300"
/>
</a>
</div>