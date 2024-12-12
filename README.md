## 실패 속에서 본질을 찾아내는 나영입니다 👋

**불확실한 상황**에서 최적의 솔루션을 찾아가는 것을 좋아합니다.<br>
'일단 돌아가는' 이 아닌 '**제대로 돌아가는**' 코드 작성을 좋아합니다.

<br>

## 📚 리소스 최적화 리스트, 근데 실패를 곁들인... 😅

- [Bloom Filter로 DB I/O 최소화](https://medium.com/@im_zero/bloom-filter%EB%A1%9C-db-%EB%B6%80%ED%95%98-%EA%B0%90%EC%86%8C-%EC%84%B1%EB%8A%A5-61-%EA%B0%9C%EC%84%A0-e46e8ce62d6d)해 성능 61% 개선
    - 154.15ms -> 59.17ms로 개선
    - Unique 제약 조건을 DB Layer가 아닌 Service Layer에서 확인

<br>

- [Kafka Streams 윈도우 집계로 DB I/O 최소화](https://medium.com/@im_zero/kafka-streams%EC%9D%98-window-results-%EC%BB%A8%ED%8A%B8%EB%A1%A4%ED%95%98%EA%B8%B0-3c20c360cf02), 그러나...😅
    - 배치 단위로 쓰기 버퍼링 목표 달성! (사용 중인 MySQL, MongoDB 쓰기 버퍼링 기능에서 아이디어 획득)
    - 그러나 Drop Event 처리를 위한 **Window + Grace 기간에 따른 버퍼링**이 메모리 문제로 이어져 적용 실패

<br>

- [Kafka Stremas Join](https://medium.com/@im_zero/kstream-ktable-join-%EC%A0%81%EC%9A%A9-%EC%8B%A4%ED%8C%A8%EA%B8%B0-f7b8bfa11e42)으로 DB I/O 50% 감소 & 처리 속도 83% 개선, 그러나...😅
    - 처리 속도 10.2s -> 1.7s 개선
    - 그러나 원천 데이터의 빠른 영속화 불가로 적용 실패

<br>

- [Hibernate Query Plan Cache 활용해 ](https://medium.com/@im_zero/hibernate-query-plan-cache-oom-%EC%97%90%EB%9F%AC-%ED%95%B4%EA%B2%B0-298f3feae93a)OOM 에러 해결
    - IN 절 padding 설정으로 최대한 같은 SQL 구문 재사용 유도
    - [@DynamicUpdate 대신 @Version 사용해 cached SQL 구문 사용](https://medium.com/@im_zero/version-vs-dynamicupdate-342d27dc59fd)

<br>

더 많은 경험을 [medium](https://medium.com/@im_zero)에서 공유하고 있습니다 💚

<br>

## 🛠️ 기술 스택

### DEV

<img src="https://img.shields.io/badge/Java-%23007396?style=flat&logo=Java&logoColor=white">

<img alt="Static Badge" src="https://img.shields.io/badge/Spring%20Boot-%236DB33F?style=flat&logo=Spring%20Boot&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Spring Data JPA-%236DB33F?style=flat&logo=Spring&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Spring Cloud Gateway-%236DB33F?style=flat&logo=Spring&logoColor=white">

<img alt="Static Badge" src="https://img.shields.io/badge/Apache%20Kafka-%23231F20?style=flat&logo=Apache%20Kafka&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Redis-%23FF4438?style=flat&logo=Redis&logoColor=white">

<img alt="Static Badge" src="https://img.shields.io/badge/Resilience4J-%23231F20?style=flat&logo=Resilience4J&logoColor=white">


### DB

<img alt="Static Badge" src="https://img.shields.io/badge/MySQL-%234479A1?style=flat&logo=MySQL&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/MongoDB-%2347A248?style=flat&logo=MongoDB&logoColor=white">

### Test & Monitoring

<img alt="Static Badge" src="https://img.shields.io/badge/JUnit5-%2325A162?style=flat&logo=JUnit5&logoColor=white">

<img alt="Static Badge" src="https://img.shields.io/badge/prometheus-%23E6522C?style=flat&logo=prometheus&logoColor=white"> <img alt="Static Badge" src="https://img.shields.io/badge/Grafana-%23F46800?style=flat&logo=Grafana&logoColor=white">

<img alt="Static Badge" src="https://img.shields.io/badge/Elastic%20Stack-%23005571?style=flat&logo=Elastic%20Stack&logoColor=white">

<br>

<div align="center">
<a href="https://github.com/devxb/gitanimals">
<img
  src="https://render.gitanimals.org/farms/imzero238"
  width="500"
  height="200"
/>
</a>
</div>