---
title: Java 테스트 규칙
summary: 테스트 코드 작성 규칙입니다.
authors:
    - Harry Jung
date: 2022-07-26
---

V2022.07.26.1

# 테스트

## 메서드명 

테스트하고자 하는 메서드명과 테스트 조건, 예상되는 결과를 테스트 메서드명으로 구성한다.
```java 
@Test
void addContentsInfo_GivenAddRequestWithMandatory_ThenReturnContentsid() {
}

@Test
void addContentsInfo_GivenNoCategoryId_ThrowNotFoundException() {
}

@Test
void toggleEmoji_GivenValidRequest_ThenSuccess() {
}
```


## 주석 명시 
테스트 코드 내에서 주어진 조건, 테스트 조건, 예상 결과를 표시하는 주석을 명시한다.
```java 
@Test
void addContentsInfo_GivenAddRequestWithMandatory_ThenReturnContentsid() {
    // given
    when(ioFrDivCategoryInfoRepository.findById(anyString())).thenReturn(mockingIoFrDivCategoryInfo());
    when(ioWorkplaceInfoRepository.findById(anyString())).thenReturn(mockingIoWorkplaceInfo());
    IoFrContentsInfo mockIoFrContentsinfo = mockingIoFrContentsInfo(null).get();
    when(ioFrContentsInfoRepository.save(any())).thenReturn(mockIoFrContentsinfo);
    // when
    CommonParamInfo commonParamInfo = new CommonParamInfo();
    commonParamInfo.setClientId("CLIENT_ID");
    String contentsId = frContentsService.addContents(commonParamInfo,
        FrContentsRequest.Add.builder().categoryId("CATEGORY_ID").title("TITLE").contents("CONTENTS").build());
    // then
    assertThat(contentsId).isEqualTo(mockIoFrContentsinfo.getContentsId());
}
```
