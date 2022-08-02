---
title: Java 메서드 규칙
summary: 메서드 정의 규칙입니다.
authors:
    - Harry Jung
date: 2022-07-26
---

V2022.07.26.1

# 메서드

## 메서드명

- 동사나 전치사로 시작한다.
- CRUD 기능과 상항에 따라 다음의 동사나 전치사를 사용할 수 있다.
    - C: add, create
    - R: get, list
    - U: update
    - D: delete
    - 조건 전치사: is, has, can

- `io` Prefix 및 `info` Surfix 를 제외하고 메서드명을 정의한다.
- 약속된 약어를 사용할 수 있다.
- (예시) `updateFrGroupFavoritesIdx`
- 사용범위를 한정하기 위해서 접미사 `by`를 사용할 수 있다.


## 정적 메서드의 `of`, `from` 사용 조건

- 파라미터가 1개일 때는 `from` 메서드를 사용한다.
- 파라미터가 2개 이상일 때는 `of` 메서드를 사용한다.


