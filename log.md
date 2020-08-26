# Spring boot log
> 스프링부트를 진행하면서 발생하는 이슈들을 정리하는 용도의 문서

## JsonPathResultMatchers_Import_Error (p.76)
: 76p에서 .andExpect(jsonPath("$.name", is(name))) .andExpect(jsonPath("$.amount", is(amount))); 부분에서 에러가 발생함.

- ErrorMessage: 
``` java
incompatible types: JsonPathResultMatchers cannot be converted to ResultMatcher .andExpect(jsonPath("$.name",is(name)))
```                
로 출력되어 테스트를 진행할 수 없었음. 

- Solve: 
```java
import static org.hamcrest.Matchers.is; 
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.jsonPath;
```

- Reference: https://youngsubee.tistory.com/entry/Spring-boot-JsonPathResultMatchers%EC%97%90%EB%9F%AC

## p.97 .build error (Proceeding)

- ErrorMessage
: https://github.com/jojoldu/freelec-springboot2-webservice/issues/455 위 링크와 동일한 증상 발생. 


