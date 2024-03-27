# 2차시\_출력\_async, defer

1. 웹 사이트 밖에서 JS 사용: node.js
2. JS의 공식 사이트: [ecma-international.org/mdn](http://ecma-international.org/mdn) docs
3. JS 선언 위치(async)
    1. 웹 브라우저는 script 태그를 만나면 잠시 HTML 분석(parsing)을 멈추고 js를 다운받는다.
    2. head에 script 태그 선언
        1. script 용량이 크면 다른 HTML 요소를 받기까지 너무 많은 시간이 소요된다.
        2. queryselector를 사용할 경우 오류가 발생할 수 있다.
    3. body의 끝 부분에 script 태그 선언
        1. script에 매우 의존적인 웹 사이트는 제대로 동작하지 않을 수 있다.
    4. async 사용

        ```jsx
        <head>
            <script async src="main.js"></script>
        </head>
        ```

        1. 브라우저가 parsing 하다가 script 태그를 만나면 HTML 요소와 script를 동시에 받는다.
        2. script를 다 받으면 script를 바로 실행한다.
        3. 문제점

            1. HTML 요소를 다 받기도 전에 script를 실행하므로 역시 queryselector 사용 시 문제가 발생할 수 있다.
            2. 여러 script 실행 시 다운받은 순서대로 실행시키므로 순서의존적인 경우 문제가 생긴다.

            ![Untitled](Lectures/DreamCoding/2_img/async.png)

    5. defer 사용

        ```jsx
        <head>
            <script defer src="main.js"></script>
        </head>
        ```

        1. HTML 요소와 script를 동시에 다운받는다.
        2. HTML 요소를 다 받은 다음 script를 실행한다.

        ![Untitled](2%E1%84%8E%E1%85%A1%E1%84%89%E1%85%B5_%E1%84%8E%E1%85%AE%E1%86%AF%E1%84%85%E1%85%A7%E1%86%A8_async,%20defer%20993e644a5706415e9edf8b77bb8d3076/Untitled%201.png)
4. **use strict(이게 있었네????)**

    1. 코드 최상단에 이거 써놓기

    ```jsx
    "use strict";
    ```
