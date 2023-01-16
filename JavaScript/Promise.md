## Promise

Promise가 있기 이전에 비동기 작업을 처리 할 때에는 콜백 함수로 처리를 했었는데, 콜백 함수로 처리하게 됐을 때 비동기 작업이 많아지면 코드가 깊어지고 복잡해지는 단점이 있었습니다.  
그래서 콜백 함수의 단점을 보안하고 비동기 작업을 조금 더 편하게 처리 할 수 있도록 ES6에 도입된 기능이 Promise입니다.  
  
Promise의 기본 문법은 아래와 같습니다.

```jsx
const promiseTest = new Promise(function(resolve, reject){
        // 코드작성
})

promiseTest.then(function(n){

}).catch(function(n){

})

// Arrow Function
const promiseTest = new Promise((resolve, reject) => {
    // 코드작성
})

promiseTest.then(n => {

}).catch(n => {

})
```

로직이 성공적으로 마무리 된다면 resolve를 호출하고 then을 사용해서 성공했을 때에 수행할 작업의 로직을 작성할 수 있고,  
실패한다면 reject를 호출하고 catch를 사용해서 실패했을 때에 수행할 작업의 로직을 작성할 수 있습니다.  
  
추가로 resolve, reject를 호출 할 때 파라미터로 값을 보내준다면 이후 수행할 로직에서 해당 데이터를 사용할 수 있게됩니다.  
여기까지만 보면 콜백 함수와 Promise의 차이점이 없어보이는데 Promise는 프로미스 체이닝으로 then과 같은 후속 처리 메소드를 연달아서 사용할 수 있어서 콜백 함수의 콜백 지옥을 해결하고 비동기 처리 시점을 명확하게 표현할 수 있습니다.

```jsx
const promiseTest = new Promise(function(resolve, reject){
        // 코드작성
})

promiseTest.then(function(n){

}).then(function(n){

}).then(function(n){

})

// Arrow Function
const promiseTest = new Promise((resolve, reject) => {
    // 코드작성
})

promiseTest.then(n => {

}).then(n => {

}).then(n => {

})
```
