로그 설정하기

@Slf4j 
롬복 사용 

로그 레벨 설정
LEVEL: TRACE > DEBUG > INFO > WARN > ERROR

application.properties
여기서 설정한다.

만약 전체 로그 레벨을 설정하고 싶다면

logging.level.root=info

패키지명에 따라

밑에는 hello.springmvc 하위에 모두 로그를 작성.
logging.level.hello.springmvc=debug

## @RestController

@Controller 는 반환 값이 String 이면 뷰 이름으로 인식된다. 그래서 뷰를 찾고 뷰가 랜더링 다. 
@RestController 는 반환 값으로 뷰를 찾는 것이 아니라, HTTP 메시지 바디에 바로 입력한다.

## @RequestMapping

대부분의 속성을 배열[] 로 제공하므로 다중 설정이 가능하다. {"/hello-basic", "/hello-go"}

## @PathVariable(경로 변수)

사용 시점

URL 경로를 템플릿화 할 수 있는데, @PathVariable 을 사용하면 매칭 되는 부분을 편리하게 조회할 수 있다.

```java
@GetMapping("/mapping/users/{userId}/orders/{orderId}") 
public String mappingPath(@PathVariable String userId, @PathVariable Long orderId) { 
	log.info("mappingPath userId={}, orderId={}", userId, orderId); 				return "ok";
}
```

변수명이 같으면 생략 가능 
@PathVariable("userId") String userId -> @PathVariable userId

## @RequiredArgsConstructor --> 생성자 주입
@RequiredArgsConstructor final 이 붙은 멤버변수만 사용해서 생성자를 자동으로 만들어준다. 

```JAVA
public BasicItemController(ItemRepository itemRepository) 
{
	this.itemRepository = itemRepository; 
} 
```

이렇게 생성자가 딱 1개만 있으면 스프링이 해당 생성자에 @Autowired 로 의존관계를 주입해준다. 따라서 final 키워드를 빼면 안된다!, 그러면 ItemRepository 의존관계 주입이 안된다.

이점: 새로운 필드를 추가할 때 다시 생성자를 만드는 번거로움을 없앨 수 있다.