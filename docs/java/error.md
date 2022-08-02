---
title: Error 처리
summary: Error 정의 및 발생 규칙입니다.
authors:
    - Harry Jung
date: 2022-07-26
---

V2022.07.26.1

# Error

## 에러 유형 정의 
- 서버에서 발생시키는 특정 에러는 고유의 코드값을 갖도록 정의한다. 
- 코드의 정의 `com.planetory.io.error.constant` 패지키 내 `interface` 파일에 상수로 작성한다.
- 기능 혹은 리소스에 따라 알파벹 대문자와 숫자로 구성된 3자리의 대분류 항목 코드를 사용한다.
- 1자리 숫자로 중분류 항목 코드를 사용한다.
- 2자리 숫자로 상세 항목 코드를 사용한다. 
- 대분류, 중분류, 상세 항목 코드를 조합해 에러코드를 정의한다.
```java
...
/* AUDIT_TYPE : A07 */
String AUDIT_CODE_BASIC_DAYOFF_ADD = "A07101"; // 휴무 추가
String AUDIT_CODE_BASIC_DAYOFF_UPDATE = "A07102"; // 휴무 수정
String AUDIT_CODE_BASIC_DAYOFF_UPDATE_IDX = "A07103"; // 휴무 수정
String AUDIT_CODE_BASIC_DAYOFF_DISABLE = "A07104"; // 휴무 추가

String AUDIT_CODE_BASIC_USER_MOD_TYPE = "A08101"; // 구성원 추가 권한

/* AUDIT_TYPE : B01 */
String AUDIT_CODE_USER_POSITION_ADD = "B01101"; // 직급 추가 > /admin/user/mgmt/position/add
...
```

## Http 반환 에러 코드의 사용 
- 상수로 정의한 샤플 에러코드는 `enum` 파일로 구체화 및 그룹화하여 사용한다.
- `com.planetory.io.error.constant.StatusCodeConstant` Enum 파일에서 Http 에러 상태 정보를 관리한다.
- `com.planetory.io.exception.ErrorCode` 인터페이스를 구현하여 다음 정보를 작성한다. 
    - http status 코드값 
    - 샤플 에러 코드 
    - 샤플 에러 메시지
- `com.planetory.io.exception.handler.ResponseErrorException` 클래스의 `of` 메서드를 이용하여 `StatusCodeConstant` 에러를 발생시킨다. 

```java 
throw ResponseErrorException.of(FrErrorCode.FR_SOLVE_NOT_ISSUE_TYPE);
```