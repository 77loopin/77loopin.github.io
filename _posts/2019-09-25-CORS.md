# CORS 

출처 : [https://developer.mozilla.org/ko/docs/Web/HTTP/Access_control_CORS](https://developer.mozilla.org/ko/docs/Web/HTTP/Access_control_CORS)

## SOP (동일 출처 정책)

- 보안 상의 이슈 때문에 동일 출처를 기본적으로 준수해야하고, 최초 요청 출처 말고 다른 곳으로 스크립트를 통해 자원을 요청하는 것은 금지된다.
ex) [naver.com](http://naver.com) 에서 ajax 로 [vlive.tv](http://vlive.tv) 로 자원 요청.

## CORS (Cross Origin Resource Sharing) 이란?

- 동일한 출처가 아니여도 다른 출처에서의 자원을 요청하여 쓸 수 있게 허용하는 구조.
- 브라우저측에서 JSONP를 사용하거나, 서버측에서 CORS를 이용하여 해결 가능하다.
- 스프링 부트에서는 @CrossOrigin 혹은 WebConfigure에서 CORS를 적용하는 방법을 제공한다.

## CORS 동작 과정

Step1) pre-flight : 실제 요청하려는 경로와 같은 URL 에 대해 HTTP OPTIONS 로 요청을 날려보고 요청가능한지 확인.

step2) 실제 요청

## 적용 방법

1. @CrossOrigin 어노테이션 사용
- Controller에서 클래스 단위나, 메소드 단위로 설정 가능.
- 브라우저에서는 **Access-Control-Allow-Origin/Access-Control-Allow-Methods**  를 헤더에 보내줘야 한다.

    @RestController
    public class DaheeController {
    	
    	@CrossOrigin(origins="http://minhee.com:163")
    	@GetMapping("/doorlock")
    	public String open() {
    		return "Welcome";
    	}
    }

2. WebConfig

- 브라우저에서는 위의 방법과 동일하게  **Access-Control-Allow-Origin/Access-Control-Allow-Methods**  를 헤더에 보내줘야 한다.

    @Configuration
    public class WebConfig implements WebMvcConfig {
    
    	@Override
    	public void addCorsMapping(CorsRegistry registry) {
    		registry.addMapping("/**")
    						.allowOrigins("http://minhee.com:163");
    	}
    }

3. JsonP

- JsonP는 HTML의 script 요소로부터 요청되는 호출에는 보안상 정책이 적용되지 않는다는 점을 이용한 우회방법.
- JsonP는 기존에 서버에서 리턴해주던 json 문자열을 callback 으로 감싸서 리턴해주는 것을 뜻한다.
ex) {"name" : "dahee", "age" : "26"} -> callback({"name":"dahee", "age":"26"});
- 클라이언트 사용 방법 : 
- jsonp 옵션은 데이터를 넘겨줄 서버에서 받은 callback 함수명 이름.

    $.ajax({
    	url: "http://dahee.com",
    	dataType: "jsonp",
    	jsonp: "callback",
    	success: () => {}
    });

## 네이버 전화면점

1. Cross-domain 피해서 ajax 를 call 하는 방법
2. CORS 해결 방법.
