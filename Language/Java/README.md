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
추상 메소드는 선언부만이 존재하고 구현부는 작성되어 있지 않습니다. 이 구현부를 자식 클래스가 오버라이딩해서 사용합니다.
추상 클래스를 만들기 위해서는 class 앞에 Abstract를 붙여야 합니다. 추상 클래스는 추상 메소드를 포함한다는 점을 제외하면 일반 클래스와 동일합니다.
추상 메소드의 사용 용도는 추상 메소드가 포함된 클래스를 상속받은 자식 클래스가 반드시 추상 메소드를 구현하기 위해서 사용하게 하기위한 용도입니다.

### Interface와 Abstract의 공통점과 차이점
#### 공통점
- 추상 클래스와 인터페이스는 선언만 있고 구현체는 존재x(Java 8 버전 부터 인터페이스에서 default 메소드로 구현이 가능하긴함)
- 인스턴스화 불가능
- 자식 클래스가 무언가 반드시 구현하도록 위임해야할 때 사용
#### 차이점
- 추상 클래스는 단일 상속만 가능하고, 인터페이스는 다중 상속이 가능
- 추상 클래스 목적은 상속을 받아서 기능을 확장 시키는 것(부모의 유전자를 물려받음)
- 인터페이스의 목적은 구현하는 모든 클래스에 대해 특정 메소드가 반드시 존재하도록 하는 것(사교적으로 필요에 따라 결함)

### Reference
   * 점프 투 자바 Interface 참고 [Link](https://wikidocs.net/217)
   * TCP SCHOOL Interface 참고 [Link](https://tcpschool.com/java/java_polymorphism_interface)
   * 점프 투 자바 Abstract 참고 [Link](https://wikidocs.net/217)
   * TCP SCHOOL Abstract 참고 [Link](https://tcpschool.com/java/java_polymorphism_abstract)
	
## Collection
Java에서 컬렉션은 데이터의 집합을 의미하며 자료구조인 컬렉션과 이를 구현하는 클래스를 정의하는 인터페이스를 제공합니다.
![collection](https://github.com/joonsu1229/interviewPrepare/blob/main/img_folder/collection.png)<br>
### Set 컬렉션(HashSet, TreeSet)
- 순서가 없는 데이터의 집합으로, 데이터의 중복을 허용하지 않습니다.<br>
![Set](https://github.com/joonsu1229/interviewPrepare/blob/main/img_folder/Set.png)<br>
Set은 위 그림처럼 비선형 구조로 되어 있어 순서가 없고, 인덱스도 존재하지 않습니다. 그렇기 때문에 값을 삭제하거나, 추가할때 속도가 굉장히 느립니다.
1. HashSet
Set 컬렉션에서 가장 많이 사용되는 클래스가 HashSet입니다. HashSet은 해시 알고리즘을 이용하기 때문에 검색속도가 빠릅니다.
입력된 순서에 상관없이 저장하며 중복값을 허용하지 않습니다. 순서를 유지해야한다면 LinkedHashSet을 이용하여야 합니다.
중복을 걸러내는 방법은 객체를 저장하기 전 먼저 hasCode() 메소드를 호출하여 같은 해시코드가 있는지 비교합니다. 같은 해시 코드가 있다면 Equals() 메소드를 사용하여 같은 객체가 있다면 중복 저장을 이용하지 않습니다.

2. TreeSet
이진 탐색트리의 형태로 데이터를 저장하는 컬렉션입니다. 데이터의 추가, 삭제에는 성능이 좋지 않지만 검색, 정렬 시 성능이 뛰어납니다. HashSet과 마찬가지로 저장순서를 유지하지 않습니다.
### List 컬렉션(ArrayList<E>, LinkedList<E>, Vector<E>)
- 요소의 저장 순서가 유지됩니다.
- 같은 요소의 중복 저장을 허용합니다.
1. ArrayList
ArrayList는 배열을 이용하기 때문에 인덱스를 사용하여 배열 요소에 빠르게 접근할 수 있습니다. ArrayList는 배열과 다르게 크기를 늘리는 과정이 자동으로 수행 되지만, 요소의 추가, 및 삭제 작업에 걸리는 시간이 오래 걸립니다.
2. LinkedList<br>
![LinkedList](https://github.com/joonsu1229/interviewPrepare/blob/main/img_folder/LinkedList.png)<br>
양방향 포인터 구조로 데이터의 삽입, 삭제가 자주 일어날 경우에 사용하기 좋습니다. ArrayList의 단점을 보완하기 위해 고안된 컬렉션입니다.
LinkedList는 양방향 연결 리스트로 구현되어 있습니다. 각각의 노드가 next(다음 노드), prev(이전 노드)의 정보를 가지고 있습니다. 이러한 특성 덕에 삭제, 삽입의 성능이 좋습니다.
3. Vecter
ArrayList와 같은 동작을 수행하는 클래스입니다. ArrayList가 사용하는 메소드와 거의 동일하지만 현재는 기존 코드와의 호환성 때문에 남아 있는 컬렉션이므로 ArrayList를 사용하는게 좋습니다.

## Map 컬렉션(HashMap, HashTable, TreeMap)
Map 컬렉션 클래스들은 Key, Value를 한 쌍으로 저장하는 Key-Value 방식을 사용합니다. Map 컬렉션 클래스의 특징은 요소의 저장순서를 유지하지 않습니다. 
그리고 키는 중복을 허용하지 않지만 값은 중복을 허용합니다.

### HashMap
![HashMap](https://github.com/joonsu1229/interviewPrepare/blob/main/img_folder/HashMap.png)<br>
HashMap은 해싱 알고리즘을 사용하기 때문에 많은 양의 데이터를 검색하는데 뛰어난 성능을 보입니다. 위 사진에서 보이듯이 key-value를 저장하는 구조를 가지고 있습니다.

### TreeMap
TreeMap은 이진트리를 기반으로 한 Map 컬렉션입니다. TreeSet과의 차이점은 TreeSet은 값만 저장하지만 TreeMap은 키와 값이 저장됩니다. 
TreeMap은 데이터가 저장될 때 정렬을 하기 때문에 HashMap보다 추가, 삭제가 오래걸립니다. 정렬 상태를 유지해야 하거나 정렬된 데이터를 조회해야할 경우에 유용합니다.
![redBlackTree](https://github.com/joonsu1229/interviewPrepare/blob/main/img_folder/redBlackTree.png)

TreeMap은 이진탐색트리가 보완된 레드-블랙-트리를 이용하여 만들어진 컬렉션입니다.

### HashTable
HashMap과 거의 유사한 기능과 사용법을 보이지만 Vector와 마찬가지로 HashTable보단 HashMap을 사용하는 것이 더 좋습니다.
HashTable은 멀티스레드 환경이 아니라면 HashMap보다 성능이 떨어집니다.
	
### Reference
   * 잡다한 프로그래밍 참고 [Link](https://crazykim2.tistory.com/589)
   * 팡트루야 티스토리 참고 [Link](https://pangtrue.tistory.com/291)
   * 코딩 팩토리 참고 [Link](https://coding-factory.tistory.com/557)

## Thread
Thread란 프로세스를 이루는 코드의 실행 흐름입니다. 프로세스에는 한 개 이상의 스레드가 존재합니다. 두 개 이상의 스레드를 가지는 프로세스를 멀티 스레드라고 합니다.
Thread 생성하는 방법은 두가지가 있습니다.
1. Runnable 인터페이스를 구현해서 하는 방법
2. Thread 클래스를 상속받는 방법
보통 1번의 방법을 많이 이용하는데 그 이유는 2번 방법을 이용했을경우 extends를 사용하기 때문에 다른 클래스를 상속받을 수 없지만, 1번의 경우 인터페이스를 구현(implements)을 이용하기 때문에 다른 클래스를 상속받는 이점이 있어 1번의 이유를 많이 사용합니다. 1번의 방식으로 예제 코드를 구현해보겠습니다.
Thread 코드를 실행해보면 예상과는 다르게 동작하는 것을 볼 수 있습니다. 예를들어 이런 코드를 작성해보겠습니다.
	
public class ThreadTest implements Runnable {
	int seq = 0;

	
	public ThreadTest(int seq){
		seq = this.seq;
	}

	@Override
	public void run() {
		System.out.println("Thread 실행-" + seq + "초");
		
		try{
			Thread.sleep(1000); // 1초로 시간제한
		}catch(Exception e){
		}
		
		System.out.println("Thread 종료")	;
	}
	
	public static void main(String[] args) {		
		for(int i=0; i < 10; i++){
			Thread t = new Thread(new ThreadTest(i));
			
			t.start();
		}
		System.out.println("프로그램 종료");
	}
}

이 코드를 실행해보면 for문에 있는 thread가 실행되기 전에 프로그램 종료라는 문구가 나옵니다. 이처럼 쓰레드를 실행하면 순서대로 진행하는것이 아닌 따로 독자적으로 실행되는 것을 알 수 있습니다.


## 동기화(Synchronized)

## Overriding과 Overloading


