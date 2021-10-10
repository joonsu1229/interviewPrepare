# Part 2-1. Javascript
* [AJAX와 Promise란?](#ajax와-promise란)
* [자바스크립트의 타입](#자바스크립트의-타입)
* [호이스팅이란?](#호이스팅이란)
* [클로저란?](#클로저란)
* [프로토타입이란?](#프로토타입이란)
* [자바스크립트의 this란?](#자바스크립트의-this란)

## AJAX와 Promise란?
### AJAX
AJAX란 자바스크립트를 사용하여 비동기 방식으로 서버와 브라우저가 데이터를 교환하는 통신 방식입니다.
보통 서버와 브라우저는 동기방식으로 동작을하여 페이지 갱신시 부분적으로 웹 화면의 일부가 변경되는것이 아닌 전체 페이지가 갱신이 되는데 웹 화면의 일부분만 변경을 하고 싶을 경우 비동기방식인 Ajax를 사용합니다. 즉 비동기 방식인 Ajax를 이용하여 갱신이 필요한 부분만 데이터를 통신하여 갱신하는 기능입니다.<br>

ex) <br>
$.ajax({ <br>
　　url:"",  //통신할 URL 입력 <br>
　　type:"POST",  //GET, POST 등 <br>
　　dataType : "json", // html, string, json 등 <br>
　　async : "true" // 동기방식으로 사용할지, 비동기 방식으로 사용할지 선택. 동기방식으로 사용할 경우 false 입력. <br>
　　success: function(result) {  <br>
　　　　//데이터 통신 성공 시 함수 작성 <br>
　　} <br>
}); <br>

### Promise
Promise는 Ajax와 같은 비동기 방식의 함수입니다. 하지만 Ajax의 단점인 콜백헬(Callback hell), 에러, 예외처리가 보완되어 ES6에 정식으로 포함되었습니다.
Promise는 비동기 처리에 성공하면 resolve라는 메소드를 호출해서 비동기 처리 결과를 후속 처리 메소드로 전달합니다. 만약 실패할 경우 reject라는 메소드가 후속처리 메소드로 전달합니다.
후속처리 메소드에는 then, catch가 있습니다. <br>

ex) <br>
function promiseTest(param) { <br>
　　return new Promise(function(resolve, reject) { <br>
　　　　if(param){ <br>
　　　　　　　resolve(); //성공 <br>
　　　　}else{ <br>
　　　　　reject(); //실패 <br>
　　　　}	 <br>
　　}); <br>
} <br>
//tehn 성공했을경우 함수호출 <br>
function success() { <br>
　　console.log("성공"); <br>
　　return false; <br>
} <br>

//catch 실패했을경우 해당 함수 호출 <br>
function error() { <br>
　　console.log("실패"); <br>
　　return false; <br>
} <br>

promiseTest(true)<br>
.then(success) //성공한 경우  <br> 
.catch(error); // 실패할 경우 <br>

### Reference 
  * 애송이의 코딩이야기 promise  [Link](https://mjn5027.tistory.com/85)

## 자바스크립트의 타입
### 자바스크립트의 Number Type과 다른 언어와의 차이점
 * 자바스크립트는 모든 수를 실수로 처리하고 있고 number 타입 하나만 존재
 * 다른 언어 처럼 int, float, double 등의 타입이 존재하지 않음
### 원시타입의 종류
string, number, bigint, boolean, undefined, ES6 부터 추가된 symbol 이 있습니다. 원시타입은 불변성을 가지고 있습니다. 불변성을 가지고 있기때문에 값을 재할당 할 경우 새로운 메모리에 재할당한 값이 저장됩니다.

### Reference
 * 박해씨의 기묘한 프로젝트 참고 [Link](https://velog.io/@nomadhash/Java-Script-%EA%B9%8A%EC%9D%80-%EB%B3%B5%EC%82%AC%EC%99%80-%EC%96%95%EC%9D%80-%EB%B3%B5%EC%82%AC)
 
## 호이스팅이란?

## 클로저란?
## 프로토타입이란?
## 자바스크립트의 this란?
