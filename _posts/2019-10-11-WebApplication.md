---
title: WebApplication
date: 2019-10-11 13:00:00
categories: ETC
tags: ETC
---

#### Q1. JAVA Servlet API이 무엇인지 설명할 수 있나요?
<details><summary style="font-size:15px">보기</summary>
  
---

자바의 서블릿 API는 JVM 위에서 실행되는 어플리케이션을 빌드하기 위한 인터페이스의 집합과 파일 정의들입니다.  
톰캣과 제티같은 웹 어플리케이션들이 자바 서블릿 API 를 구현하고 있습니다.

---

</details>

#### Q2. 서블릿 API는 어떻게 웹 어플리케이션을 정의하나요?
<details><summary style="font-size:15px">보기</summary>
  
---

서블릿 API 는 web.xml이라는 배포 명세서를 사용하여 웹 애플리케이션을 정의한다.  
Web.xml 에서 서블릿을 정의하고 서블릿 컨테이너가 서블릿을 어떻게 구성하고 제공할지도 정합니다.


---

</details>


</details>

#### Q3. WAR 파일이 뭔가요?
<details><summary style="font-size:15px">보기</summary>
  
---

웹 아카이브 파일인 WAR는 자바의 JAR 파일과 같은 역할을 합니다.  
파일 안에는 애플리케이션을 실행하기 위해 컴파일 된 모든 클래스 파일/프로퍼티 파일/설정 파일들도 포함되어 있습니다.
WAR 파일의 가장 중용한 점은 웹 어플리케이션을 어떻게 설정할지 정의판 배포 명세서(web.xml) 이 있다는 것입니다.
이 파일은 어플리케이션 서버에게 어플리케이션을 어떻게 배포하고 제공할 지에 관한 내용을 명령으로 제공합니다.

---

</details>

#### Q4. HTTP란 무엇이고 특징을 말해보세요.
<details><summary style="font-size:15px">보기</summary>  
  
--- 

인터넷 상에서 데이터를 주고받기 위한 프로토콜.  

특징은 Connectionless와 Stateless 입니다.  
Http 는 기본적으로 서버에 연결을 요청하고 응답을 받으면 연결을 끊어 버리는 connectionless한 방식으로 동작합니다.  
즉, 자원 하나에 하나의 연결을 만듭니다.  
따라서 불특정 다수를 다루는 서비스에 적합하기 때문에, 수십만명이 웹 서비스를 사용하더라도 접속 유지는 최소한으로 할 수 있습니다.  
이러한 특징때문에 클라이언트의 이전 상태를 알 수가 없는데, 이러한 HTTP의 특성을 Stateless 라고 합니다.  
이를 해결하기 위해 Cookie를 사용합니다.  

---

</details>

#### Q5. HTTP 메서드 아는대로 말해보시요.
<details><summary style="font-size:15px">보기</summary>
  
---

GET : 자원 제공  
POST : 자원 새로 설정  
PUT : 자원 업데이트  
DELETE : 자원 삭제  
HEAD : GET 과 비슷하지만 응답코드와 헤더만 반환. ex) 자원 존재하는지만 확인.  

---

</details>

#### Q6. HTTP 응답코드 아는거 설명/400과 500의 차이  
<details><summary style="font-size:15px">보기</summary>  
  
---

2XX : 요청과 응답이 성공적이라는 뜻   
200 : 성공  
201 : PUT 요청을 반환하며 자원이 생성되었다고 알려줌.  
204 : (No Contents) 요청은 성공했지만 클라이언트에게 추가정보를 제공하지 않는다.  

3XX  
301/302 : Redirect  

4XX : 클라이언트가 유효한 요청을 만드는 데 실패.  
400 : Bad Request. 잘못된 요청을 보내는 경우.  
403 : Forbidden. 권한이 없는 경우  
404 : 요청한 자원이 존재하지 않는다.  
405 : Method Not Allowed. 잘못된 HTTP 메서드를 이용했다.  

5XX : 서버측에 이슈가 있다는 것을 알려줌.  
500 : Internal server Error. 일반적인 메시지. 서버 전체를 이용할 수 없는 상황이 아니라 일부 특정 자원 하나 또는 몇 개의 자원만 이용할 수 없는 경우.  
503 : Service Unavailable. 현재 서버를 이용할 수 없다.  
504 : Gateway Timeout.  

---

</details>


#### Q7. HTTPS 란?
<details><summary style="font-size:15px">보기</summary>  
  
---

정보를 암호화하는 SSL 프로토콜을 이용하여 데이터를 전송하고 있다는 뜻입니다.
SSL 이란 공개키와 비공개키를 이용하여 서로에게 신뢰도 있는 데이터를 전송합니다.  
서버에서 클라이언트에게 뿌린 공개적인 키로 클라이언트가 보내는 데이터는 이 공개키로 암호화 되어서 서버에 보내집니다.  
공개키로 암호화된 정보는 서버에만 있는 개인키로만 해독이 가능하기 때문에제 3자가 암호화된 정보를 가로채더라도 서버의 개인키가 없는 한 복호화가 불가능하다. 이와 같은 원리로 HTTP 보다 더 안전하게 통신을 할 수 있습니다.
---

</details>





***
war/ 압축 여부는 tomcat에서 설정 가능.
