# Part 1-1. 웹 개발 상식
* [객체지향의 개념](#객체지향의-개념)
* [MVC 패턴의 개념](#mvc-패턴의-개념)
* [쿠키와 세션의 공통점과 차이](#쿠키와-세션의-공통점과-차이)
* [RESTful API 개념](#restful-api-개념)
* [SSO의 개념](#sso와-ssl의-개념)

## 객체지향의 개념
객체지향의 개념은 가장 기본이지만 굉장히 어려운 단어라 생각합니다. 지금도 정확하게 알지는 못하지만 면접 준비를 하며 객체 지향 프로그래밍(OOP)의 개념을 다시 정확히 숙지하기 위해 정리합니다.<br>
객체 지향 프로그래밍은 각각의 기능들을 객체라는 기본 단위로 나누고(독립적), 이 객체들 간의 상호작용을 통해 프로그램을 설계하고 개발하는 것 입니다.<br>
객체지향의 장점은 각각의 객체들로 이루어져 독립적인 성격을 갖고 있기 때문에 하나의 객체를 수정하여도 다른 객체에 영향이 가지 않는 의존성이 낮은 약한 결합관계입니다. 이러한 특성덕에 유지보수하는 측면에 있어 상대적으로 적은 범위의 코드만 수정해도 되기 때문에 유지 비용이 적게 듭니다. <br>
또한 캡슐화라는 특징이 있는데 속성과 행위가 관련이 있는 것들을 묶는 것입니다. 중요한 부분은 외부에서 접근이 필요한 부분을 제외하고 내부로 숨기는 것입니다(보안).<br>
캡슐화라는 특징 덕에 프로그래밍의 신뢰성 또한 높습니다. 다만 단점으로는 객체간의 의존성, 독립성 등을 생각하며 프로그래밍을 해야하기 때문에 설계하는 부분에 있어 시간이 느린 점, 실행속도가 느린 단점이 있습니다.

### 객체지향 5가지 원칙
1. SRP (Single Responsibility Principle) : 단일 책임 원칙
   - 하나의 클래스는 하나의 책임만 가져야한다.
2. OCP (Open-Closed Principle) : 개방 폐쇄 원칙
   - 확장에는 개방되어 있어야 하고 변경에는 폐쇄 되어 있어야 한다.
3. LSP (Liskov Substitution Principle) : 리스코프 치환 원칙
   - 객체는 프로그램의 정확성을 깨지 않으면서 하위 타입의 인스턴스로 바꿀수 있어야 한다.
4. ISP (Interface Segragation Principle) : 인터페이스 분리 원칙
   - 인터페이스는 그 인터페이스를 사용하는 클라이언트를 기준으로 분리한다.
5. DIP (Dependency Inversion Principle) : 의존관계 역전 원칙
   - 구체적인 클래스보다 인터페이스나 추상 클래스와 관계를 맺어야 한다.


### Reference 
  * Perter의 우아한 프로그래밍 [Link](https://gracefulprograming.tistory.com/130)

## MVC 패턴의 개념
![MVC](https://github.com/joonsu1229/interviewPrepare/blob/main/img_folder/MVC%20pattern.jpg)

### MVC의 개념
Controller(컨트롤러)<br>
클라이언트가 요청을 했을때, 그 요청을 처리할 수 있는 비지니스 로직이 구현되어 있는 모델 컴포넌트를 호출한다. 그리고 클라이언트가 보낸 데이터를 모델에 전달하기 쉽게 가공한다.
이후 비지니스 로직이 구현되어 있는 모델이 처리를 완료하면 그 결과를 VIEW에게 전달한다.

Model(모델)<br>
컨트롤러가 호출하는 컴포넌트이다. 실제 요청된 업무를 처리하는 비지니스 로직을 구현하는 영역으로 데이터 등을 처리한다. DB에 연결하여 데이터를 조회, 저장, 삭제, 업데이트 등의 작업을 요청한다.
데이터를 처리한 후 다시 컨트롤러에 결과를 반환한다.

View(뷰)<br>
컨트롤러로부터 받은 결과 데이터를 이용하여 사용자가 보게 될 화면을 만드는 역할을 한다. (Html, Css, Javascript를 모아둔 컨테이너)

### Reference
   * MVC 패턴 참고 링크 [Link](https://asfirstalways.tistory.com/180)

## 쿠키와 세션의 공통점과 차이
### 쿠키
쿠키는 웹 사이트에 접속할 때 생성되는 정보를 담은 임시파일 입니다. 데이터의 형태는 Key와 Value로 구성되어 있습니다.<br>
쿠키는 서버에 저장하는 대신 사용자의 컴퓨터에 저장되는 데이터입니다. 쿠키의 사용 목적으로는 방문 했던 사이트 로그인 정보 자동 <br>입력 , 팝업 "오늘 이 창을 다시 보지않기", 쇼핑몰 장바구니 등에 사용됩니다.<br>
쿠키의 단점으로는 사용자의 PC에 데이터를 저장하다보니 임의로 고치거나 지울 수 있고, 가로채기도 쉬워 보안에 취약합니다.
### 세션
세션은 서버에 저장되는 데이터로서 웹 브라우저 당 1개씩 생성되며 웹 컨테이너에 저장됩니다. 웹 서버에 접속한 시점부터 웹 브라우저를 종료하기까지 사용자의 상태를 일정하게 유지시키는 기술입니다. 
서버에서 관리하므로 쿠키보다 보안이 좋습니다.

![쿠키와 세션 차이](https://github.com/joonsu1229/interviewPrepare/blob/main/img_folder/cookie%20and%20session.png)
### Reference
   * 쿠키, 세션의 특징 참고 [Link](https://hahahoho5915.tistory.com/32)
## RESTful API 개념
REST란 자원을 이름으로 구분하여 해당 자원의 상태를 주고받는 것을 의미합니다. 구체적인 개념은 HTTP URI를 통해 자원을 명시하고, HTTP Method를 통해 해당 자원에 대한 GET, PUT, DELETE, POST 등의 CRUD를 적용하는 것을 의미합니다. 즉, REST API란 REST 기반으로 서비스 API를 구현한 것 입니다. <br>  RESTful이란 REST의 원리를 따르는 시스템을 의미합니다.
### REST API의 특징
   * REST 기반으로 시스템을 분산해 확장성과 재사용성을 높일 수 있다.
   * HTTP를 지원하는 프로그램 언어로 클라이언트, 서버를 구현할 수 있다(Java, C# 등을 이용해 클라이언트 제작 가능).

### Reference
   * RESTful API 참고 링크 [Link](https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html)

## SSO의 개념
   * SSO(Single Sign-On) : 한번의 로그인으로 여러가지 다른 사이트들을 자동적으로 접속하여 이용하는 방법. 즉 하나의 시스템에서 인증을 한 경우 타 시스템에서는 인증정보가 있는지 확인 후 정보가 있으면 로그인 처리를 하도록 하는 것입니다.

### Reference 
   * SSO참고 링크 [Link](https://brunch.co.kr/@sangjinkang/36)

## SSL의 개념
SSL(Secure Socket Layer) 프로토콜은 처음에 Netscape사에서 웹서버와 브라우저 사이의 보안을 위해 만들었습니다. SSL은 Certificate Authority라 불리는 서드 파티로부터 서버와 클라이언트의 인증을 하는데 사용됩니다. ![SSL](https://github.com/joonsu1229/interviewPrepare/blob/main/img_folder/ssl.png)<br>
자세한 내용은 하단의 참조한 사이트에서 숙지하시길 바랍니다.

### Reference 
   * [SSL 개념 및 동작 원리 알아보기](https://goodgid.github.io/TLS-SSL/)
   * [HTTP와 SSL에 대한 기본 개념 및 통신과정](https://jins-dev.tistory.com/entry/SSL-%EC%9D%B4%EB%9E%80-SSL-%EC%97%90-%EB%8C%80%ED%95%9C-%EC%A0%95%EB%A6%AC)

