# Part 1-2. 네트워크
* [TCP와 UDP의 개념](#tcp와-udp의-개념)
* [GET과 POST의 차이](#get과-post의-차이)
* [HTTP와 HTTPS 차이](#http와-https-차이)
* [OSI 7계층](#osi-7계층)

## TCP와 UDP의 개념
TCP와 UDP는 전송계층에서 사용하는 프로토콜로써, 목적지까지 전송한 패킷을 상위의 특정 프로토콜에게 전달하는 것에 목적이 있습니다.

### TCP(Transmisstion Control Protocol)의 특징
 * TCP는 연결형 서비스를 지원하는 프로토콜입니다.
 * 연결형 서비스로 가상 회선 방식을 제공
 * 높은 신뢰성을 보장
 * 데이터의 전송 순서 보장
 * UDP보다 전송속도가 느림
### UDP(User Datagram Protocol)의 특징
 * 비연결형 서비스를 지원하는 전송 계층 프로토콜로써, 정보를 일방적으로 전달하는 통신.
 * 정보를 주고 받을대 정보를 보내거나 받는 다는 신호절차를 거치지 않는 단방향 통신.
 * 신뢰성 없는 데이터를 전송
 * TCP보다 전송속도가 빠름
 
### Reference 
 * TCP와 UDP 참고 링크 [Link](https://choseongho93.tistory.com/3)

## GET과 POST의 차이
### GET의 개념
HTTP/1.1의 RFC2616을 확인해보면 GET은 서버로부터 정보를 조회하기 위한 메서드입니다. GET은 요청을 전송할 때 필요 데이터를 쿼리스트링을 통해 전송합니다. URL의 마지막 부분에 ?와 함께 이름과 값으로 쌍을 이루는 요청을 쿼리스트링이라 합니다. <br> ex) www.XXXX.com?name=value&name2=value2 <br>
&는 여러개의 데이터를 전송할 때 사용합니다. GET 방식은 데이터를 전송할때 URL에 노출되어 전송하기 때문에 보안면에서 POST보다 좋지 않습니다. 또한 보낼 수 있는 데이터에 한계가 있습니다.

### POST의 개념
POST는 리소스를 생성/변경하기 위해 전송할 데이터를 Body에 담아서 전송합니다. Body에 담아서 데이터를 전송하기 때문에 여러 데이터를 전송할 수 있습니다. 겉으로 노출되는 데이터가 없기 때문에 GET보다 보안적인 측면이 조금은 낫다할수 있겠지만 Fidder, 개발자 도구 등을 사용하여 보내는 데이터를 다 확인할 수 있습니다. 

### GET과 POST의 차이
GET은 서버에 동일한 요청을 여러번해도 동일한 응답이 돌아와야 합니다. 그래서 GET은 조회 데이터를 요청할 때 사용해야 합니다. POST는 동일한 요청을 하더라도 응답이 다를 수 있습니다. POST는 데이터의 상태를 변경시킬 때 사용합니다.

### Reference
 * GET과 POST의 차이 [Link] (https://hongsii.github.io/2017/08/02/what-is-the-difference-get-and-post/)
 * 
## HTTP와 HTTPS 차이
HTTP는 인터넷에서 웹 서버와 사용자의 컴퓨터에 설치된 웹 브라우저 사이에 문서를 전송하기 위한 통신 규약이다. HTTP는 텍스트 교환이기 때문에 네트워크에서 신호를 가로채어 본다면 내용이 노출된다. 이러한 보안상의 문제를 해결하기 위해 등장한 것이 HTTPS다. HTTP에 SSL 프로토콜을 이용하여 보안상의 문제를 해결한 것이다. HTTPS는 인터넷 상에서 정보를 암호화하여 웹 브라우저와 서버가 데이터를 주고받는 통신 규약이다.

### Reference
 * HTTP와 HTTPS의 차이 [Link](https://jeong-pro.tistory.com/89)
 
## OSI 7계층

### Reference 
   * 


