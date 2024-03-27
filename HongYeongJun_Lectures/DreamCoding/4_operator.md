# 4차시_연산자

1. 논리 연산자
    1. or 연산에서 자원 절약
        
        ```jsx
        console.log(`or: ${aa||bb||check()});
        ```
        
    
    or는 하나라도 true이면 즉시 조건문 계산을 중지하므로 got te=het 
    
2. 등호
    1. ===: type까지 같아야 true를 반환한다. 
    2. Object 등호
        
        ```jsx
        const ellie1 = {name: 'ellie'};
        const ellie2 = {name: 'ellie'};
        const ellie3 = ellie1;//ellie1을 참조한다
        console.log(ellie1 == ellie2);//false
        console.log(ellie1 === ellie2);//false
        console.log(ellie1 === ellie3);//true
        ```
        
3. 테스트
    1. true
    2. false
    3. true
    4. false
    5. true
    6. false
4. switch
    
    ```jsx
    const browser = 'IE';
    switch (browser)
    	case 'IE':
    		console.log("Go away!");
    		break;
    	case 'Chrome':
    	case 'FireFox':
    		console.log("Love you!");
    		break;
    	default:
    		console.log("Same all!");
    		break;
    		
    ```