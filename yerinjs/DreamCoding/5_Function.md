## 1

- function name(param1, param2){body...return}
- 하나의 함수는 하나의 기능만 해야 한다.
- 함수 이름은 동사로 한다. (예시: doSomething)
- 함수 이름이 너무 정하기 어려우면 하나의 기능만 있는지 생각해야 한다.
- JS에서 함수는 Object이다.

```jsx
function printHello() {
  console.log("Hello");
}
```

## 2. Parameters

- Primitive Parameters는 값이 함수에 전달된다.
- Object Parameters는 참조가 함수에 전달된다.

```jsx
function changeName(obj) {
  obj.name = "coder"; //들어온 name 변수가 coder 값을 가리킨다.
}
const ellie = { name: "ellie" };
changeName(ellie);
console.log(ellie);
```

1. 만약 changeName(ellie) 함수가 Parameter를 value로 전달했다면...(call by value)
   1. Swap 영역에 ellie 객체가 복사된다.
   2. 복사된 ellie 객체의 name 변수 값이 coder 값을 가리킨다.
   3. 복사된 객체는 함수가 종료되는 즉시 사라지므로 아무 일도 일어나지 않는다.
2. 만약 changeName(ellie) 함수가 Parameter를 ref로 전달했다면...(call by reference)
   1. 이제 이 함수는 ellie 객체를 직접 건드린다.
   2. ellie 객체의 name 변수 값이 coder 값을 가리킨다.
   3. 정상적인 결과값이 나온다.

## 3. Default Parameters(added in ES6)

- 과거

```jsx
function showMessage(message, from){
 if (from === undefined){
  from = 'unknown';
}
 console.log(`${message} by ${from});
}
showMessege('Hi~');//Hi~ by unknown
```

- 현재

```jsx
function showMessage(message, from = 'unknown'){
 console.log(`${message} by ${from});
}
showMessege('Hi~');//Hi~ by unknown
```

## 4. Rest Parameters(added in ES6)

```jsx
function printAll(...args){//Parameter가 배열 형태로 전달된다
for let( i = 0; i < args.length; i++){
console.log(args[i]);
}
for (const arg of args){
 consolee.log(arg);
}
}
```

## 5. Scope

- 자식 함수는 부모 함수의 변수에 접근할 수 있지만 부모 함수는 자식 함수의 변수에 접근할 수 없다.

## 6. Early Return

```jsx
function upgrade(point){
 if point <= 10{
 return;
 }
else{
 //long upgrade logic
 }
}
```

## 7. Function Expression

```jsx
print(); //print는 변수로 선언됐으므로 에러 난다.
print2(); //print2는 함수로 선언됐으므로 호이스팅된다.
const print = function () {
  //anonymous function
  console.log("print");
};
const printAgain = print;
printAgain();
function print2() {
  console.log("print2");
}
```

## 8. Callback Function

- 전달인자로 다른 함수에 전달되는 함수를 뜻한다.

```jsx
function randomQuiz(answer, printYes, printNO) {
  //printYes와 printNo는 함수
  if (answer === "love you") {
    printYes();
  } else {
    printNo();
  }
}
```

## 9. Arrow Function

```jsx
const Num = function add(a, b) {
  return a + b;
};
```

```jsx
const Num = (a, b) => a + b;
```
