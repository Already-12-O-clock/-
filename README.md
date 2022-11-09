# 가나다라영화사 (ABCDmoviE)

- 멋쟁이사자처럼 프론트엔드 스쿨 3기 아쉬워 벌써12시조 토이프로젝트

## 프로젝트 소개

- KMDb OpenAPI를 이용하여 최신 영화 정보 및 관심있는 영화의 상영 정보를 파악하는 웹 어플리케이션

---

## 프로젝트에 사용된 기술 및 정보

### 프로젝트에 사용된 기술

- HTML
- CSS
- JavaScript

### 프로젝트에 사용된 API 정보

- [KMDb OpenAPI](https://www.kmdb.or.kr/info/api/apiDetail/6)

### 프로젝트에 사용된 컨벤션

1. git Convention<sup>[1](#footnote_1)</sup><sup>[2](#footnote_2)</sup>

- 커밋 메시지는 다음과 같은 형식을 지켜 작성합니다.

```
$ git commit -m "<type>(<scope>): <short summary>
<줄바꿈>
<body>
<줄바꿈>
Breaks: <주요 변경 내역 요약>
<줄바꿈>
<줄바꿈>
<이슈 상태> #<이슈번호>
"
```

- `<type>`에 작성하는 항목

  - feat : 새로운 기능 추가

  - fix : 버그 수정

  - docs : 문서 관련

  - style : 스타일 변경 (포매팅 수정, 들여쓰기 추가, …)

  - refactor : 코드 리팩토링

  - test : 테스트 관련 코드

  - build : 빌드 관련 파일 수정

  - ci : CI 설정 파일 수정

  - perf : 성능 개선

* 참고 예시

  - 1번 예시

    ```
    $ git commit -m "feat($plusTime): plusTime 함수 추가 (addTime)

    추가시간 버튼을 클릭 시 해당 버튼에 기록된 시간만큼 타이머에 시간을 추가하는 함수:
    - 버튼에 이벤트 발생시 각 버튼의 텍스트 숫자값을 ms로 변환하여 addTime 변수에 저장
    - addTime 변수를 argument로 받아 타이머의 잔여 시간에 추가

    Breaks: setTime 함수의 인자로 추가된 addTime을 제거함


    Close #123
    "
    ```

  - 2번 예시

    ```
    $ git commit -m "doc($README.md): 2022-11-09 회의 내용

    주요 회의 내용:
    - git 컨벤션 설정 (./11.09/git_Convention_Details.md)
    - 페이지 구현 방안 (./11.09/Readme.md)
    - 각 구현 페이지별 주 관리자 역할 분담 (./11.09/Readme.md)
    - 전반적인 웹페이지 workflow 구성 (./11.09/Readme.md)
    - PR 관련 규칙(생성 시기, PR용 branch 작명, PR 작성) (./11.09/Readme.md)
    - 기본 웹페이지 스타일 구성 (./11.09/Readme.md)

    Breaks: README.md Skills 내용 수정 (Scss -> CSS)


    Close #2
    "
    ```

  - 3번 예시

    ```
    $ git commit -m "refactor($banana): banana 전역 변수 제거

    banana 변수를 전역 스코프가 아닌 moreBanana 함수 블록 스코프 지역 변수로 변경:
    - banana 변수를 전역 변수로 할당하여 발생하는 신뢰성 이슈 제거
    - banana 변수가 전역 객체인 windows와 동일한 생명주기를 가져 발생하는 메모리 이슈 제거

    Breaks: $moreBanana 함수 수정

      Before:

      let banana = hitButtonTimes;

      function moreBanana() {
        return banana;
      }


      After:

      function moreBanana(hitButtonTimes) {
        let banana = hitButtonTimes;
        return banana;
      }
    "
    ```

- 세부적인 작성 방법 안내는 [여기](./minutes/11.09/git_Convention_Details.md)를 눌러주세요.

<a name="footnote_1">1</a>: [AngularJS git Commit Message Conventions](https://gist.github.com/stephenparish/9941e89d80e2bc58a153) 참조
<a name="footnote_2">2</a>: [AngularJS git Commit Message Conventions 번역글](https://velog.io/@outstandingboy/Git-%EC%BB%A4%EB%B0%8B-%EB%A9%94%EC%8B%9C%EC%A7%80-%EA%B7%9C%EC%95%BD-%EC%A0%95%EB%A6%AC-the-AngularJS-commit-conventions)
