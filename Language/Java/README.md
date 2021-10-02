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
예외란 error의 일종이며 예외 발생 시 프로그램 오류가 발생하게 됩니다. 오류가 발생했을때 에러를 무시하고 그대로 프로그램을 진행시키고 싶을 수도 있고, 에러가 났을 경우 해당 에러를 해결하기 위한 처리를 하는 코드를 작성할 때도 있다. 이러한 경우들에 대비하여 Java는 try..catch, throw, finally 등을 이용하여 에러 처리할 수 있도록 도와준다.
예외처리는 굉장히 중요한 부분으로 항상 신경써야 한다. <br>
	
### 예외처리를 하기 위한 기본 구문<br>
try { <br>
	...<br>
}catch () { <br>
	... <br>
} <br>
<br> try 안에는 실행되는 소스 코드를 구현한다. catch은 try문 안의 코드에서 오류가 발생했을 경우 실행된다. 오류 발생시 catch문을 통해 어떤 오류가 발생했는지 메시지를 남길 수도 있고, 다양한 경우에 사용한다. catch() 괄호 안에 다양한 예외를 명시할 수 있다. <br>
자바의 예외에는 일반 예외(Checked Exception), 실행 예외(Unchecked Exception)으로 분류된다.
일반 예외는 개발자가 직접 처리를 진행하여야 하고 실행 예외는 try-catch로 처리하기 보단 예외가 발생하지 않도록 주의하여야 한다.
그리고 finally라는 구문이 있다. finally는 오류가 발생했을 경우에도 프로그램이 종료되는 것이 아닌 반드시 실행되어야 하는 코드가 있을 경우에 작성한다.
	
### Reference
   * 예외처리 참고 [Link](https://wikidocs.net/229)

## Interface와 Abstract
### Interface
자바는 클래스를 통한 다중 상속을 허용하지 않습니다. 하지만 다중 상속의 이점을 버릴 수는 없기 때문에 자바에서는 인터페이스를 통한 다중 상속을 지원합니다. 인터페이스란 다른 클래스를 작성할 때 기본이 되는 틀을 제공합니다. 인터페이스는 추상 메소드와 상수만을 포함할 수 있습니다. 인터페이스를 선언하는 방법은 접근 제어자와 함께 interface 키워드를 사용하면 됩니다.<br>
ex) 접근제어자 interface 인터페이스 이름{...}<br>	
	
인터페이스의 장점
1. 프로젝트 개발 시 일관되고 정형화된 개발을 위한 표준화가 가능합니다.
2. 클래스의 작성과 인터페이스의 구현을 동시에 진행할 수 있으므로, 개발 시간을 단축할 수 있습니다.
3. 클래스와 클래스 간의 관계를 인터페이스로 연결하면, 클래스마다 독립적인 프로그래밍이 가능합니다.

### Abstract
추상 메소드란 자식 클래스에서 반드시 오버라이딩을 해야 사용할 수 있는 메소드입니다. 인터페이스의 역할도 하면서 구현체도 가지고 있는 클래스입니다.
추상 클래스를 만들기 위해서는 class 앞에 Abstract를 붙여야 합니다. 추상 클래스는 추상 메소드를 포함한다는 점을 제외하면 일반 클래스와 동일합니다.
### Interface와 Abstract의 차이

### Reference
   * 점프 투 자바 Interface 참고 [Link](https://wikidocs.net/217)
   * TCP SCHOOL Interface 참고 [Link](https://tcpschool.com/java/java_polymorphism_interface)
   * 점프 투 자바 Abstract 참고 [Link](https://wikidocs.net/217)
   * TCP SCHOOL Abstract 참고 [Link](https://tcpschool.com/java/java_polymorphism_abstract)
	
## Collection

## Thread

## 동기화(Synchronized)

## Overriding과 Overloading


