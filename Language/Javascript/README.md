# Part 2-1. Javascript
* [AJAX와 Promise란?](#ajax와-promise란)
* 

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
