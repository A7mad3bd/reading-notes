# Spring intro

## Build Simple Spring Application 
---
## Summary 
- Built a static homepage that accepts a GET request at `http://localhost:8080/greeting`
- In Spring's approach to building web sites HTTP requests are handled by a controller. You can identify this by `@Controller` annotation. 
- The `@GetMapping` annotation ensure that HTTP GET requests to `/greeting` are mapped to the `greeting()` method.
- The implemetation of the method body relies on a view technology to perform server side renderings of the HTML. Thymeleaf pareses the `greeting.html` template and evaluates the `th:text` expression to render the value of the `${name}` paramter that was set in the controller. 

## Spring Boot Devtools
- A common feature of developing web applications is coding a change, restatrting your application, and refreshing the browser to view the change. This eats up a lot of time. `spring-boot-devtools` allows
- enables **Hot Swapping**
- Switches template enginers to diable caching.
- Enables LiveReload to automatically refresh the browser.
- Other reasonable defaults based on development instead of production.

### Running the application 
 gradle by using `./gradlew bootRun`.

## Spring MVC and Thymeleaf: how to access data templates.
In a typical Spring application, @Controller claasses are responsible for preparing a model map with data and selecting a view to be rendereed. This makes all the defined variables availalbe to expressions executed in templates.

### Process includes
 Spring Model Attributes / Request Parameters / Session Attribute / ServletContext Attributes / Spring beans

## Resources/Citations

- [Serving Web MVC](https://spring.io/guides/gs/serving-web-content/)
- [Spring MVC ](https://www.thymeleaf.org/doc/articles/springmvcaccessdata.html)
