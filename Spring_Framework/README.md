# Part 3. Spring Framework
* [Spring Framework 란?](#spring-framework-란)
* [Spring Framework의 특징](#spring-framework의-특징)
* [Spring Boot 란?](#spring-boot-란?)

## Framework
스프링 프레임워크에 들어가기에 앞서 프레임워크란 무엇인지 정리해보았습니다. 프레임워크란 프로그램의 흐름을 제어함으로서 개발자가 어떠한 틀에 맞춰 개발을 하도록 유도하는 것입니다. 
틀을 만듦으로써 개발 생산성을 향상 시키고 개발을 더욱 쉽게 만들어줍니다. 라이브러리와는 다소 차이가 있으니 주의하시기 바랍니다.
라이브러리는 간단하게 말자면 전체적인 프로그램의 흐름은 개발자에 맡기며 특정한 기능을 하는 코드를 개발자가 직접 선택하여 사용하는 것입니다.

## Spring Framework 란?
스프링 프레임워크란 자바를 위한 오픈 소스 프레임워크로 자바 기반 엔터프라이즈 애플리케이션 개발을 위해 다양한 서비스를 제공해주는 프레임워크 입니다.
스프링 프레임워크는 개발자가 개발에만 집중할 수 있도록 도와주는 역할을 합니다. 

## Spring Framework의 특징
스프림 프레임워크의 특징은 크게 4가지가 있습니다. 경량 컨테이너,  제어 역행(IOC), 의존성 주입(DI), 관점지향 프로그래밍(AOP) 등의 특징이 있습니다.
#### 경량
 * 과거엔 EJB(Enterpise Java Bean)이 컨테이너 역할을 해주었는데 이것보다 더 경령화된 컨테이너로 등장한 것이 Spring Framework
 * Spring은 톰캣과 같은 단순 서버 환경에서도 동작하며 단순한 개발환경으로도 엔터프라이즈 애플리케이션을 개발가능
 * 간편한 애플리케이션 개발이 가능하며 생산성이 뛰어난 프레임워크

#### 제어역행(Inversion Of Control, IOC)
 * 메소드나 객체의 호출작업을 개발자가 결정하는 것이 아니라, 외부에서 결정되는 것을 의미
 * 개발자가 객체 생성에 관련된 코드를 직접 작성하는 것이 아닌 프레임워크가 객체를 생성하여 반환하고 코드를 동작하는 순서를 결정

#### 의존성 주입(Dependency Injection, DI)
 ![DI](https://github.com/joonsu1229/interviewPrepare/blob/main/img_folder/DI.png)<br>
 DI는 객체를 개발자가 생성하는 것이 아닌 외부에서 생성을 시킨 후 주입시켜주는 것 입니다. 위의 사진 처럼 객체를 생성하는 방법은 2가지가 있습니다. 첫번째 방법은 New 생성자를 사용하는 방법, 두번째 방법은 setter()나 생성자를 통해 사용하는 방법입니다. 2번 방법이 직접 생성하지않고 외부에서 생성된 객체를 생성자나 setter()로 사용하는데 이걸 스프링에서 사용하는 DI라고 합니다.<br>
 * 의존성이란 객체가 혼자서 처리할 수 없음을 뜻함
 * 제어의 역행을 사용해서 특정 객체를 필요한 객체의 외부에서 생성ㅎ

#### 관점지향 프로그래밍(Aspected oriented programming, AOP)
 * 핵심적인 관점, 부가적인 관점으로 나누어보고 그 관점을 기준으로 모듈화 하는것이 AOP
 * AOP의 목표는 공통으로 사용하는 기능은 외부의 독립된 클래스로 분리하고, 개발자가 해당 기능을 선언하여 적용하는것
 * AOP는 프록시 패턴이라는 디자인 패턴을 사용
 * Aspect : 여러 곳에서 중복되는 코드를 뜻하는 단어
### Reference
  * Spring 참고 [Link](https://private.tistory.com/39)
## Spring Boot 란?
Spring Boot란 기존의 Spring Framework의 다양한 설정의 어려움 등을 자동화하여 Spring Framework 기반으로 등장한 프레임워크입니다. 개발자가 개발에 집중할 수 있도록 기존 스프링 프레임워크에서 설정하던 다양한 파일들을 패키징하여 간편하게 제공하였습니다.

#### Spring Boot의 특징
 * Starter라는 기능을 이용하여 기존 Spring MVC의 Dependency를 자동화 하였습니다.
 * 설정을 자동화 하였습니다.
 * 내장 Tomcat을 사용하여 별도의 WAS를 구성하지 않고 바로 개발할 수 있습니다.
 * 라이브러리 버전 자동 관리
#### Spring Boot Starter 기본적인 종류
![SpringBoot Starter](https://github.com/joonsu1229/interviewPrepare/blob/main/img_folder/starter.png)
### Reference
 * Spring Boot 참고 [Link](https://incheol-jung.gitbook.io/docs/q-and-a/spring/spring-boot)
