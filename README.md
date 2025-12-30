# Redis Demo (Spring Boot)

## 개요

* Spring Boot + Redis 연동 데모
* 문자열 Key / Value 저장·조회

## 기술 스택

* Java 21
* Spring Boot 3.5.8
* Spring Data Redis
* Gradle
* Redis 6.x 이상

## 사전 준비

* Java 21 설치
* Redis 실행
* 포트: `6379`

## Redis 실행 (Docker)

```bash
docker run -d --name redis-demo -p 6379:6379 redis:6.2.2
```

## 프로젝트 실행

```bash
./gradlew bootRun
```

## API 목록

* 값 저장

  ```
  GET /redis/set?key={key}&value={value}
  ```
* 값 조회

  ```
  GET /redis/get?key={key}
  ```

## 테스트 예시

```bash
curl "http://localhost:8080/redis/set?key=test&value=hello"
curl "http://localhost:8080/redis/get?key=test"
```

## Redis 설정

* Key Serializer: String
* Value Serializer: String
* RedisTemplate 사용

## 용도

* Redis 기본 연동 확인
* 로컬 / 데모 환경 테스트

## 주의사항

* 인증 없음
* TTL 미사용
* 단일 Redis 기준

---
