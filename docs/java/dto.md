---
title: Java DTO 규칙
summary: DTO 정의 규칙입니다.
authors:
    - Harry Jung
date: 2022-07-26
---

V2022.07.26.1

# DTO

## DTO 파일 생성 규칙

- DB Entity 가 있는 경우 그에 대응하는 DTO 파일을 생성한다.
- `io` Prefix 및 `info` Surfix 를 제외하고 파일명 및 클래스명을 정의한다.
- 약속된 약어를 사용할 수 있다.
- 사용자의 요청을 전송하는 Request DTO를 만들 수 있다.
    -  `/dto/request/${도메인}Request.java` 형태로 제작한다. 
    - (예시) `fr/v2/dto/request/FrGroupRequest.java`
- 사용자에게 응답하는 Response DTO를 만들 수 있다.
    - `/dto/response/${도메인}Response.java` 형태로 제작한다. 
    - (예시) `fr/v2/dto/response/FrGroupResponse.java`
- 각 도메인 별 요청 DTO와 응답 DTO 내에 해당 도메인의 CRUD 등 여러 형태를 하위 클래스 형태로 모아서 관리한다.
- 각 도메인 별 하위 DTO를 상속받아 사용할 경우 
    - 최상위 클래스의 네이밍은 `Simple`로 한다.
    - 상속받는 개수가 적다면(3개 이하) `Simple` 없이 `Info` 를 기본 클래스로 사용하는 것이 가능하다.
- DTO 파일의 명명규칙 예시 
    - 게시판 > 설정 > 그룹 > 대표 이미지 저장의 경우
    - Fr(게시판)Mgmt(설정)Group(게시판그룹)Image(사진)Save(동작)Request 형식으로 정의한다.
    - 대상을 계층에 따라(게시판,보고서 등) 먼저 명시하고 동작(예시_Save,Add) 입력 후 Request 또는 Response로 이름짓기를 마무리 한다.

