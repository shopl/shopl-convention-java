---
title: Java 컨트롤러 규칙
summary: 컨트롤러 정의 규칙입니다.
authors:
    - Harry Jung
date: 2022-07-26
---

V2022.07.26.1

# Controller

## URL 규칙
RESTFul 방식을 사용한다.

- 소문자를 사용한다.
- 언더바 대신 하이픈을 사용한다.
- URL의 마지막에는 슬래시를 포함하지 않는다.
- 계층관계를 나타낼 때는 슬래시 구분자를 사용한다.
- 파일 확장자는 포함시키지 않는다.
- 전달하고자 하는 자원의 명사를 사용한다. 
- 전달하고자 하는 자원의 복수형을 사용한다.(?)
- 리소스에 대한 작업 Http Method를 이용하여 구분하고 URL에 포함시키지 않는다.
- 필터링을 위해서는 쿼리스트링 파라미터를 사용한다.

## 반환 데이터
- 컨터롤러의 기본 응답 클래스는 `ResponseEntity`를 사용한다.
- 목록 데이터를 요청하는 컨트롤러의 기본 반환 형태는 `ResponseEntity<java.util.List<OOOResponse.DetailDTO>>` 형태를 사용한다.
- 사용자의 수정, 삭제, 추가 요청을 처리하는 컨트롤러의 기본 반환값은 Http 상태 코드와 메시지이다.
- 컨트롤러가 응답 시 사용하는 기본 클래스는 `com.planetory.io.spl.dto.ResultBodyDto`이다.

