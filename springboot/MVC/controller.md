# Controller
사용자의 요청을 처리하는 구성요소이다.

## 종류
- @Controller : 응답형식을 HTML로 반환하는 컨트롤러
- @RestController : 응답형식을 JSON으로 반환하는 컨트롤러

## 예제
~~~java
@RestController
public class SampleController{
    
    @PostMapping("/order")
    public String createOrder(){
        return "Created Order";
    }
    
    @GetMapping("/order/1")
    public String getOrder(){
        return "orderId: 1, Amount: 1000";
    }
    
    @RequesMapping(value="/order/2",method = RequestMethod.GET)
    public String getOrder2(){
        return "orderId: 2, Amount: 2000";
    }
    
}
~~~
### 어노테이션 분석
- @RestController : 해당 클래스가 RestController임을 스프링에게 지시
- @RequestMapping(value, method) : 메서드를 호출하는 주소와 메서드가 담당하는 요청을 지시
- @PostMapping("url")
- @GetMapping("url")