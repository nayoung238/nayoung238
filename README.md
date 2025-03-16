## 👋 실패 속에서 본질을 찾아내는 나영입니다

**불확실한 상황**에서도 응답은 빠르고 비용은 최소화한 최적의 솔루션을 만드는 것을 좋아합니다.

<br>

## 🔨 리소스 최적화 리스트, 근데 실패를 곁들인...

#### [IDOR 수평적 권한 상승](https://github.com/nayoung238/Banking-API?tab=readme-ov-file#idor-insecure-direct-object-reference-%ED%95%B4%EA%B2%B0) 이슈 해결
- JWT (Bearer Auth) 기반 인증 강화
- 데이터 설계 및 URL 변경

<br>

#### [CompletableFuture 기반 Open API 설계](https://github.com/nayoung238/Banking-API?tab=readme-ov-file#completablefuture-%EA%B8%B0%EB%B0%98-open-api-%EC%84%A4%EA%B3%84)

- Open API 호출 제한으로 네트워크 비용 절감
- 락을 완전 배제한 스레드 상태 전환

<br>

#### [Bloom Filter로 DB I/O 최소화](https://medium.com/@nayoung238/bloom-filter%EB%A1%9C-db-%EB%B6%80%ED%95%98-%EA%B0%90%EC%86%8C-%EC%84%B1%EB%8A%A5-61-%EA%B0%9C%EC%84%A0-e46e8ce62d6d)해 처리 속도 61% 개선

- 처리 속도 **154.15ms → 59.17ms**로 단축
- Unique 제약 조건을 DB Layer가 아닌 Service Layer에서 확인

<br>

#### Lua Script로 처리 속도 81.9% 개선 및 네트워크 비용 절감
<img width="700" alt="lua_script_session_callback_performance_result" src="https://github.com/user-attachments/assets/9bd0b0df-c675-4f1d-bdd0-0bae625d1740" />

- Redis 트랜잭션 구현 시 [SessionCallback](https://github.com/nayoung238/E-commerce-API/blob/main/coupon-api/src/main/java/com/ecommerce/couponservice/redis/manager/CouponStockRedisManager.java#L55)에서 [Lua script](https://github.com/nayoung238/E-commerce-API/blob/main/coupon-api/src/main/java/com/ecommerce/couponservice/redis/manager/CouponStockRedisManager.java#L121) 로 리팩토링
- 여러 명령어 일괄 전송해 네트워크 비용 절감
- 처리 속도 **2.73s → 0.495s**로 단축

<br>

#### Kafka Streams 윈도우 집계로 DB I/O 최소화, 그러나...

- **배치 단위로 쓰기 버퍼링 목표 달성** (MySQL, MongoDB 쓰기 버퍼링 기능에서 아이디어 획득)
- 카프카 스트림즈 윕도우 합계 [Topology](https://github.com/nayoung238/E-commerce-API/blob/main/item-api/src/main/java/com/ecommerce/itemservice/kafka/config/StockAggregationTopology.java#L41)
- ❌ 그러나 Drop Event 처리 → **Window + Grace 기간에 따른 버퍼링**이 메모리 문제로 이어져 적용 실패

<br>

#### Kafka Streams [KStream-KTable Join](https://github.com/nayoung238/E-commerce-API/blob/main/order-api/src/main/java/com/ecommerce/orderservice/kafka/config/streams/KStreamKTableJoinConfig.java#L83)으로 DB I/O 50% 감소 및 처리 속도 83% 개선, 그러나...

- 처리 속도 **10.2s -> 1.7s**로 단축
- ❌ 그러나 원천 데이터의 빠른 영속화 불가로 적용 실패

<br>

#### CI/CD 파이프라인 개선해 처리 속도 68.9% 개선
- CI workflow에 [gradle 패키지 캐싱 단계](https://github.com/nayoung238/Banking-API/blob/develop/.github/workflows/build-and-test-ci.yml#L39) 추가해 처리 속도 68.9% 개선
- **4m 4s -> 1m 16s** 단축

<br>

더 많은 경험을 [medium](https://medium.com/@nayoung238)에서 공유 중... 💚

<br>

## 🛠️ Tech Stack

<div align="center">

### DEV

<img alt="Static Badge" src="https://img.shields.io/badge/java17-%23007396?style=for-the-badge&logo=java&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Spring%20Boot-%236DB33F?style=for-the-badge&logo=Spring%20Boot&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Spring Data JPA-%236DB33F?style=for-the-badge&logo=Spring&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Spring Cloud Gateway-%236DB33F?style=for-the-badge&logo=Spring&logoColor=white"><br>
<img alt="Static Badge" src="https://img.shields.io/badge/Apache%20Kafka-%23231F20?style=for-the-badge&logo=Apache%20Kafka&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Resilience 4J-%23231F20?style=for-the-badge&logoColor=white">


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