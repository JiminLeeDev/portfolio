# 로드맵

## TODO

### 개발환경 구축

- [x] github repository 생성

  - [x] 브랜치 분류하여 생성
  - [ ] vscode setting

### 설계

- [ ] 기능 정의
- [ ] 기술스택 정하기
- [ ] 일정

### 구현

## 브랜치 분류 규칙

생각나는대로 바로 써내려가며 구현하는 것도 즐겁지만, 시간이 지난 후에 다시 살펴볼 때 불편한 점이 있어 브랜치를 분류하여 개발할 예정입니다. 한 브랜치에는 한 개의 README 파일만 사용될 예정이며 브랜치는 아래 작성된 리스트처럼 크게 세 종류로 분류하여 생성 후 관리 예정입니다. 자세한 내용은 하단에 위치한 각 브랜치에 대한 설명과 참고자료로 작성한 테이블 참고 부탁드리겠습니다.

- 설계
- 기능
- 수정

### 설계

설계용 브랜치는 실제로 코드를 작성하며 기능 추가 및 유지 보수를 하기에 앞서 문서화할 때 사용할 예정입니다. 기능과 수정 브랜치의 경우와는 다르게 문서화를 위해 남겨놓은 브랜치이기에 기능이 구현되거나 이슈가 해결된다고 하더라도 유지할 생각입니다. 또한 설계 브랜치에서는 큰 그림을 보며 대략적인 길을 제시하며 기록하는 것에 의미를 두었기 상세한 내용을 작성치는 않을 예정입니다.

### 기능

기능 브랜치는 설계 브랜치에서 문서화 한 후 실제적인 구현에 대한 상세 내용 문서화를 진행하며 함께 코드 작성을 하며 사용할 예정입니다. 또한 기능 추가와 관련된 상세 내용만 작성할 것이기에 전체적인 프로젝트 관리 및 일정에 대한 내용은 작성치 않을 예정입니다.

### 수정

수정 브랜치는 설계 브랜치에서 문서화 한 후 실제적인 이슈 해결에 대한 상세 내용 문서화를 진행하며 함께 코드 작성을 하며 사용할 예정입니다. 또한 이슈 해결과 관련된 상세 내용만 작성할 것이기에 전체적인 프로젝트 관리 및 일정에 대한 내용은 작성치 않을 예정입니다.

### 참고자료

|                    | 설계                                                                             | 기능                                                             | 수정                                                                            |
| ------------------ | -------------------------------------------------------------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| 작성할 내용        | 일정,<br /> 전체적인 계획에 관한 내용, <br /> 기능 추가나 수정사항에 대한 기록   | 코드,<br /> 실제적인 구현에 대한 상세 내용 문서화                | 코드,<br />이슈 관련 상세내용, <br />실제적인 이슈 해결에 대한 상세 내용 문서화 |
| 작성하지 않을 내용 | 기능 구현이나 이슈 해결에 대한 상세 내용,<br />일부 브랜치에만 해당되는 상세내용 | 기능 구현 관련한 일정,<br />전체적인 브랜치에 영향을 끼치는 내용 | 이슈 해결 관련한 일정,<br />전체적인 브랜치에 영향을 끼치는 내용                |

## 기능정의

### 렌더링 방식

#### CSR VS SSR VS SSG

전반적인 사용자 경험에 많은 영향을 끼치는 렌더링 방식에 대해 CSR, SSR 그리고 SSG는 각자의 장단점이 있기에 프로젝트에 어떤 방식을 사용할지 고민이 되었습니다. 우선 CSR, SSR 그리고 SSG의 차이점을 아래의 테이블로 정리해보았습니다.

|                  | CSR        | SSR    | SSG    |
| ---------------- | ---------- | ------ | ------ |
| 렌더링 주체      | 클라이언트 | 서버   | 서버   |
| 서버 부하        | 적음       | 많음   | 적음   |
| SEO              | 불리함     | 유리함 | 유리함 |
| 첫 로딩 시간     | 느림       | 빠름   | 빠름   |
| 페이지 전환 시간 | 빠름       | 느림   | 빠름   |
| 동적 페이지 여부 | O          | O      | X      |

포트폴리오 사이트의 용도를 생각해보았을 떄 매번 페이지를 동적으로 재생성해서 보여줄 필요가 없다고 판단했습니다. SSG의 경우 정적페이지만 지원되는 단점이 있지만, 포트폴리오 사이트에 동적 페이지 생성이 주가 될 것 같지는 않았기에 SSG를 사용하기로 결정했습니다.
