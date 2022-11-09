# git Commit Convention 상세 안내

- Created at 2022-11-09
- Modified at 2099-99-99

  cf. [커밋 메시지를 여러 줄 입력하는 방법](https://ucong-9796.tistory.com/321)

  ```
  <type>(<scope>): <short summary>
  <BLANK LINE>
  <body>
  <BLANK LINE>
  <footer>
  ```

- 위 커밋 메시지 형식에 들어가는 내용은 다음과 같습니다.

- 커밋 메시지 헤더 (Commit Message Header) : 변화에 대한 간결한 설명을 포함

  ```
   커밋 메시지 헤더
    <type>(<scope>): <short summary>
    │       │             │
    │       │             └─⫸ 명령문, 현재 시제로 작성합니다. 대문자를 사용하지 않으며, 마침표로 끝내지 않습니다.
    │       │
    │       └─⫸ Commit Scope: animations|bazel|benchpress|common|compiler|compiler-cli|core|
    │                          elements|forms|http|language-service|localize|platform-browser|
    │                          platform-browser-dynamic|platform-server|router|service-worker|
    │                          upgrade|zone.js|packaging|changelog|dev-infra|docs-infra|migrations|
    │                          ngcc|ve
    │
    └─⫸ Commit Type: build|ci|docs|feat|fix|perf|refactor|test
  The <type> and <summary> fields are mandatory, the (<scope>) field is optional.
  ```

- `<type>`에 들어갈 수 있는 항목

  - feat : 새로운 기능 추가

  - fix : 버그 수정

  - docs : 문서 관련

  - style : (코드) 스타일 변경 (Format 수정, 들여쓰기 추가, 세미콜론 추가, …)

  - refactor : 코드 리팩토링

  - test : 테스트 관련 코드

  - build : 빌드 관련 파일 수정

  - ci : CI 설정 파일 수정

  - perf : 성능 개선

  - ~~chore : 그 외 자잘한 수정~~

- `<scope>`에 들어갈 수 있는 항목

  - 변경사항에 대한 키워드를 작성

  - 함수 변경시 함수 이름을 작성하거나, 메소드 추가시 변경된 해당 클래스 이름을 작성

  - 예) $location, $browser, $compile, $rootScope, ngHref, ngClick, ngView, 등

- `<short summary>` (요약 설명)

  - 명령문, 현재 시제로 작성

  - (영문 작성시) 첫글자는 대문자가 아닌 소문자로 작성

  - 좋은 예) change

  - 나쁜 예) ~~Change~~, ~~changed~~, ~~changes~~

  - 문장의 마지막에 마침표(.) 사용 금지

- `<body>` (메시지 본문)

  - 명령문, 현재 시제로 작성

  - 변경 이유와 변경 전과 후의 차이점 설명

- `<footer>` (메시지 하단)

  - 주요 변경 사항들 (Breaking Changes)

    - 모든 주요 변경 내역들은 다음과 같이 하단에 언급

      - 변경점 (description of the change)

      - 변경 사유 (justification)

      - 마이그레이션 지시 (migration instructions)

    - 해결된 이슈 (Referencing Issues)

      - 해결된 이슈는 커밋 메시지 하단에 `Closes #<이슈번호>` 와 같이 기록

        ```
        Closes #234
        ```

      - 해결된 이슈가 여러 개인 경우는 다음과 같이 작성

        ```
        Closes #123, #245, #992
        ```

      ```
      BREAKING CHANGE: <주요 변경 내역 요약>
      <BLANK LINE>
      <변경점 + 마이그레이션 지시>
      <BLANK LINE>
      <BLANK LINE>
      Fixes #<이슈번호>
      ```

      ```
      BREAKING CHANGE: isolate scope bindings definition has changed and
        the inject option for the directive controller injection was removed.

        To migrate the code follow the example below:

        Before:

        scope: {
          myAttr: 'attribute',
          myBind: 'bind',
          myExpression: 'expression',
          myEval: 'evaluate',
          myAccessor: 'accessor'
        }

        After:

        scope: {
          myAttr: '@',
          myBind: '@',
          myExpression: '&',
          // myEval - usually not useful, but in cases where the expression is assignable, you can use '='
          myAccessor: '=' // in directive's template change myAccessor() to myAccessor
        }

        The removed `inject` wasn't generaly useful for directives so there should be no code using it.
      ```
