|    Date    |  Time   |
|:----------:|:-------:|
| 2022-10-09 | 오후 1:44 |

---

# 스프링 중간고사 예상 문제



23문제 중 선택하여 중간고사 출제함

1. 스프링 프레임워크의 동작 순서대로 작성하시오.
```java
        URL요청 ->( Controller ) -> ( Service ) -> ( Mapper ) -> ( database ) -> ( JSP )
```


2. 스프링 프레임워크와 스프링 부트 프레임워크의 특징과 차이점은 작성하시오.
```java
        - 스프링 프레임워크 특징 :
        1. IoC (Invertion of Control: 제어 역행)
        2. DI(Dependency Injection: 의존성 주입)
        3. AOP(Aspect-Oriented Programming: 관점 지향 프로그래밍)
        
        - 스프링 부트 프레임워크 특징 :
        스프링 프레임워크를 사용하기 위한 설정의 많은 부분을 자동화
        
        - 차이점 :
        1 - Embed Tomcat을 사용하기 때문에 따로 톰켓을 설치하거나 매번 버전 관리를 하지 않아도 된다.
        2 - starter를 통한 dependency 자동화
        Spring framework에서는 각각의 dependency들의 호환되는 버전을 일일이 맞추어 주어야 했고,
        하나의 버전을 올리고자 하면 다른 dependeny에 까지 영향을 미쳐 version관리에 어려움이 많았다.
        하지만 starter가 대부분의 dependency를 관리해주기 때문에 번거로움이 적어졌다.
        3 - XML 설정을 하지 않아도 된다.
        4 - jar file을 이용해 자바 옵션만으로 손쉽게 배포가 가능하다.

출처 : https://rma7.tistory.com/77
```

3. @Controller 어노테이션에 대해 자세히 설명하시오.
```java
Spring 프레임워크에서 Controller인지 인식 가능하게 하며
view(화면)로 return하는 것이 주 목적이다.

/** 3장 27p
Controller와 Service 등 다른 자바파일들과의 차이점
- JSP 문법에서만 존재하는 session, request를 사용할 수 있음
- JSP 문법이 사용가능하기 때문에 각 URL호출에 대해 처리 가능
**/
```

4. @Service 어노테이션에 대해 자세히 설명하시오.
```java
Service Class에서 쓰이며 비즈니스 로직을 수행하는 Class라는 것을 나타내는 용도이다.

/** 3장 33p
 Service는 Controller에서 자신을 찾을 수 있도록 반드시 자신의 이름을 기입함
 또한 반드시 자기 이름 앞에 I를 붙인 인터페이스를 생성하고 구현(implements)함
 **/
```

5. @Mapper 어노테이션에 대해 자세히 설명하시오.
```java
Interface를 매퍼로 등록하기 위해 @Mapper 어노테이션을 사용

```

6. SQL 언어를 XML 파일에 작성하여, 소프트웨어의 유지보수를 쉽게 하기 개발된 오픈소스 프레임워크는 무엇인가?
```java
Mybatis
```

7. Lombok 외부 라이브러리에 대해 자세히 설명하시오.
```java
Lombok 프레임워크
- 스프링 프레임워크에 적용 가능한 프레임워크
자주 사용되는 자바 코드 작성을 쉽게 작성하기 위해
어노테이션(@)으로 코드를 작성함
```

8. JDBC에 대해 자세히 설명하시오.
```java
Java DataBase Connecivity
자바 프로그램 안에서 SQL을 실행하기 위해 데이터베이스를 연결해주는 기능
```

9. DTO에 다음과 같이 정의된 변수에 @Setter 어노테이션을 작성하면, 어떤 함수가 자동으로 생성되는가?
```java
        private String user_id;

        public void setUser_id(String user_id){
            this.user_id = user_id;
        }
```



10. DTO에 다음과 같이 정의된 변수에 @Getter 어노테이션을 작성하면, 어떤 함수가 자동으로 생성되는가?
```java
        private String user_id;

        public String getUser_id(){
            return user_id;
        }
```



11. @Resource 어노테이션에 대해 자세히 설명하시오.
```java
@Autowired와 마찬가지로 Bean 객체를 주입함
Resource는 이름으로 연결해줌

```

12. @RequiredArgsConstructor 어노테이션에 대해 자세히 설명하시오.
```java
final이나 @NonNull인 필드 값만 파라미터로 받는 생성자를 추가한다.
final: 값이 할당되면 더 이상 변경할 수 없다.
```

13. 비밀번호를 암호화하기 위한 암호화 알고리즘 예와 그 알고리즘에 대해 자세히 설명하시오.
```java
SHA-256
단방향 암호화 기술인 해시 암호화 사용함, 절대 암호를 풀 수 없어야함
```

14. 식별정보(이메일, 계좌번호 등)를 암호화하기 위한 암호화 알고리즘 예와 그 알고리즘에 대해 자세히 설명하시오.
```java
AES 128-CBC 함호화 알고리즘 사용
암호화 및 복호화 지원
암호화와 복호화에 사용되는 동일한 키 존재함
```

15. 메일 발송을 위해 사용되는 프로토콜을 작성하시오.
```java
SMTP(Simple Mail Transfer Protocol)
```

16. 공지사항의 글 작성을 위해 PK컬럼의 값을 자동으로 증가시키기 위한 SQL을 작성하시오.
```java
( SELECT NVL( MAX(A.NOTICE_SEQ), 0 )+1 FROM NOTICE A )
```

17. @Slf4j 어노테이션에 대해 자세히 설명하시오.
```java
스프링 프레임워크에서 로그 처리하는 인터페이스 기술이며
로그 처리 기술인 log4j와 logback과 인터페이스 역할 수행함
스프링 프레임워크는 기본으로 logback을 채택해서 로그 처리함  -3장 27p
```

18. @GetMapping, @PostMapping, @RequestMapping 어노테이션에 대해 자세히 설명하시오.
```java
 - @GetMapping :
 RequestMapping의 축약형, @RequestMapping(value = "/test7", method = {RequestMethod.GET})
 - @PostMapping :
 RequestMapping의 축약형, @RequestMapping(value = "/test7", method = {RequestMethod.POST})
 - @RequestMapping :
 - URL 을 컨트롤러의 메서드와 매핑할 때 사용하는 어노테이션
 - 요청 주소(url) 설정, 요청 방식(GET, POST, DELETE, PATCH) 설정
 - 요청방식들을 동시에 설정 가능
@RequestMapping(value = "/test7", method = {RequestMethod.GET, RequestMethod.POST})
```

19. Controller의 ModelMap 객체에 대해 자세히 설명하시오.
```java
modelmap.addAttribute() 함수를 사용하여 Model에 데이터를 저정 후 view에서 데이터에 접근이 가능
Model 객체는 컨트롤러에서 데이터를 생성해 이를 JSP 즉 View에 전달하는 역할을 합니다.
HashMap 형태를 갖고 있고, 키(key)와, 밸류(value) 값을 저장합니다.
        
```

20. 다음과 같은 HTML의 form 태그의 요소들로부터 값을 받기 위한 Controller의 함수를 작성하시오.
```java
        <form method="post" action="/loging">
        <input type="text" name="user_id" />
        <input type="text" name="password" />
        <input type="submit" value="전송" />
        </form>
```
```java 6장 29p
@PostMapping("/loging")
public String loging(HttpServletRequest request, Model model) throws Exception {
    log.info(this.getClass().getName()+".loging Start!!");
    
    String user_id = CmmUtil.nvl(request.getParameter("user_id"));
    String password = CmmUtil.nvl(request.getParameter("password"));
    
    log.info(this.getClass().getName()+".loging End!!");
    return "교수님 사랑해요";
}
```

21. 스프링 부트 프레임워크 주요 환경설정을 정의하는 파일명은 무엇인가?

```java
application.properties - 3장 14p
```

22. 자바 외부 라이브러리를 자동으로 다운로드 및 프로젝트 자동 반영시켜는 도구의 이름과 설정 파일명을 작성하시오.
 > - 빌드 도구 : maven
 > - 설정 파일 : pom.xml

23. @Transactional 어노테이션에 대해 자세히 설명하시오.
```java
클래스, 메서드위에 @Transactional 이 추가되면,
이 클래스에 트랜잭션 기능이 적용된 프록시 객체가 생성된다.
이 프록시 객체는 @Transactional이 포함된 메소드가 호출 될 경우,
PlatformTransactionManager를 사용하여 트랜잭션을 시작하고, 
정상 여부에 따라 Commit 또는 Rollback 한다.
출처: https://goddaehee.tistory.com/167 [갓대희의 작은공간:티스토리]
```


#빅데이터연계실습 #예상문제