V2022.07.25.1

# 일러두기

샤플앤컴퍼니 서버 개발팀의 Java 관련 컨벤션 문서입니다.
현재 컨벤션 마련을 위해 논의를 시작하고 있는 단계이며, 이 문서는 지속적으로 업데이트될 예정입니다.

기본적인 컨벤션은 [캠퍼스 핵데이 Java 코딩 컨벤션](https://naver.github.io/hackday-conventions-java)을 따릅니다.


## 문서 편집 규칙

* 문서 제작 및 수정 시 가장 첫 줄에 `V${YYYY.MM.DD}.${해당일자의 수정 순서}` 와 같이 버전을 명시합니다.
* `# 문서 제목` 으로 시작합니다.
* 각 세부항목은 `## 세부 제목` 으로 구분합니다.

## 문서 개발 및 배포 방법 안내

본 문서를 제작하기 위해 사용한 도구는 [mkdocs.org](https://www.mkdocs.org)에서 찾을 수 있습니다. 
다음과 명령어를 사용하여 개발과 배포를 진행할 수 있습니다.

* `mkdocs serve` - 로컬에서 개발 시 실시간 변경사항을 반영합니다.
* `mkdocs build` - 정적 웹사이트를 제작하기 위해 사용합니다. `/site` 디렉토리에 결과물이 생성됩니다.