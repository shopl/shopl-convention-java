---
title: Java 서비스 규칙
summary: 서비스 정의 규칙입니다.
authors:
    - Harry Jung
date: 2022-07-25
---

V2022.07.25.1

# Service

## Service 파일 및 클래스명 형식

- DB Entity 가 있는 경우 그에 대응하는 Service 파일을 생성한다.
- `io` Prefix 및 `info` Surfix 를 제외하고 메서드명을 정의한다.
- 약속된 약어를 사용할 수 있다.
    - (예시) `fr/v2/service/FrGroupService.java`


## 주석

- Service 클래스의 메서드에는 해당 메서드의 역할을 설명하는 주석을 반드시 작성한다.
