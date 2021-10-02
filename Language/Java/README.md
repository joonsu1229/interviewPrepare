# Part 2-1. Java
* [람다식(Lambda Expressions)](#람다식lambda-Expressions)
* [Stream](#stream)
* [예외처리](#예외처리)
* [Interface와 Abstract](#interface와-abstract)
* [Collection](#collection)
* [Thread](#thread)
* [동기화(Synchronized)](#동기화synchronized)
* [Overriding과 Overloading](#overriding과-overloading)

## 람다식(Lambda Expressions)
람다 함수는 익명 함수를 지칭하는 용어입니다. 함수를 보다 단순하게 표현하는 방법으로 람다의 특징은 함수의 이름을 가질 필요가 없습니다. 또한 람다식으로 선언된 함수는 1급 객체이기 때문에 Stream API 매개변수로 전달이 가능합니다.

### 람다함수의 장점
1. 코드의 간결성 - 불필요한 반복문을 사용하지 않아도 되고, 복잡한 식을 단순하게 표현할 수 있습니다.
2. 지연연산 수행 - 불필요한 연산을 최소화 할 수 있습니다.
3. 병렬처리 가능 - 멀티쓰레드를 활용하여 병렬처리 가능 합니다.

### 람다식 사용법
(매개변수, ...) -> {실행문 코드}
-> 기호는 매개 변수를 이용해서 중괄호 {} 바디를 실행한다는 뜻입니다.

### Reference 
  * 람다식 참고 링크 [Link](https://galid1.tistory.com/509)

## Stream
Stream은 자바 8에서 추가된 람다를 활용할 수 있는 기술입니다. Stream은 배열 또는 컬렉션 인스턴스에 함수를 조합하여 원하는 결과를 필터링하고 결과를 얻을 수 있습니다. 이전엔 컬렉션을 다루려면 for, foreach문을 사용하여 로직이 복잡해질수록 코드의 양이 많아졌지만 Stream을 활용하여 람다식을 이용하면 코드의 양을 줄이고 간결하게 표현할 수 있습니다.
스트림은 크게 세가지로 분류할 수 있습니다.<br>
1. 생성하기 : 스트림 인스턴스 생성
2. 가공하기 : 원하는 결과를 만들어가는 작업
3. 결과 : 최종 결과를 만들어내는 작업

자바 6 이전에는 ArrayList에서 요소를 순차적으로 처리하려면 Iterator라는 반복자를 사용했습니다. 하지만 자바 8부터 추가된 스트림을 사용하면 코딩이 간결해집니다.
이전에 Iterator를 사용하여 순차처리를 한다면 <br>
ArrayList<Integer> arrList = new ArrayList<Integer>(Arrays.asList(1,2,3));
Iterator<Integer> iter = list.iterator();
while(iter.hasNext()) {
    int num = iter.next();
    System.out.println("값 : "+num);
}
 이렇게 작성하였다면 람다식 사용을 하면 이렇게 작성을 할 수 있습니다.
		ArrayList<Integer> arrList = new ArrayList<Integer>(Arrays.asList(1,2,3));
		Stream<Integer> stream = arrList.stream();
		stream.forEach(num -> System.out.println("출력 : " + num)); <br>
 
위 예시는 Stream forEach라는 기능을 나타낸 것인데 실제로는 많은 기능이 있습니다. 해당 기능을 여기서 다 정리하긴 힘들어 정리가 잘 되어 있는 링크를 참조합니다.
 
### Reference
  * Stream 참고 링크 [Link](https://futurecreator.github.io/2018/08/26/java-8-streams/)
  
## 예외처리

### Reference
   * 
## Interface와 Abstract

## Collection

## Thread

## 동기화(Synchronized)

## Overriding과 Overloading


