# 3차시_데이터 타입

1. var vs. let
    1. hoisting
        1. 선언 위치와 관계없이 선언부를 무조건 제일 위로 끌어올리는 것
        2. var는 hoisting이 적용되므로 선언도 하기 전에 값을 할당하거나 출력할 수 있다. 
    2. block scope 무시
        1. 다른 블록에 쓰더라도 전역 변수처럼 작동한다. 
    3. 결론: 제발 let 써라!!
    4. IE 개발시에는 ES6으로 개발하고 BABEL로 ES5나 ES4로 내린다. 
2. const
    1. 한번 값을 할당하면 다시 값을 변경할 수 없다. (immutable)
    2. 장점
        1. 보안
        2. thread safety
        3. 실수 방지
    3. **가능하면 const 쓰기**
3. primitive data type: 더 이상 쪼개지지 않는 데이터
    1. number: 이거 하나로 숫자는 전부 해결
    2. string
        1. 템플릿
        
        ```jsx
        const b = 'brendan'
        const hi = `hi ${b}`//hi brendan
        ```
        
    3. symbol: 변수를 유일한 값으로 만든다. 괄호 안에 들어가는 것은 symbol 이름으로 디버깅을 쉽게 하기 위해 붙인다. 
        
        ```jsx
        const symbol1 = Symbol('id');
        const symbol2 = Symbol('id');
        console.log(symbol1 === symbol2);//false
        ```
        
        ```jsx
        const gsymbol1 = Symbol.for('id');
        const gsymbol2 = Symbol.for('id');
        console.log(gsymbol1 === gsymbol2);
        console.log(`value: ${gsymbol1.description}, type : ${typeof gsymbol1}`);
        //symbol은 .description으로 문자열로 바꾸어야 출력된다. 
        ```
        
4. Mutable data types vs. Immutable data types
    1. Immutable
        1. let score = 300; 이렇게 선언하면