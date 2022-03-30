
### Spring Boot and OAuth2

- Using social login
- Either Googele or GitHub
- OAuth2.0 and Spring Boot
- Run main in SocialApplication
  
### Single Sign On with GitHub

- Add homepage by creating an index.html
- Add in Jquery and Twitter Bootstrap
[Credit](https://spring.io/guides/tutorials/spring-boot-oauth2/)

- GitHub acts as a resource server that verifys your info and sends out a token

- You'll  change the client side with JQuery

````Java
@SpringBootApplication
@RestController
public class SocialApplication extends WebSecurityConfigurerAdapter {

    // ...

    @Override
    protected void configure(HttpSecurity http) throws Exception {
    	// @formatter:off
        http
            .authorizeRequests(a -> a
                .antMatchers("/", "/error", "/webjars/**").permitAll()
                .anyRequest().authenticated()
            )
            .exceptionHandling(e -> e
                .authenticationEntryPoint(new HttpStatusEntryPoint(HttpStatus.UNAUTHORIZED))
            )
            .oauth2Login();
        // @formatter:on
    }

}
````

[Oauth2 gradle](https://docs.spring.io/spring-security-oauth2-boot/docs/2.1.8.BUILD-SNAPSHOT/reference/html5/)

````Java
dependencies {
  compile 'org.springframework.boot:spring-boot-starter-security'
  compile 'org.springframework.security.oauth.boot:spring-security-oauth2-autoconfigure:2.1.8.BUILD-SNAPSHOT'
}
````

[Setup](https://spring.io/guides/tutorials/spring-boot-oauth2/)

````Java
$.ajaxSetup({
  beforeSend : function(xhr, settings) {
    if (settings.type == 'POST' || settings.type == 'PUT'
        || settings.type == 'DELETE') {
      if (!(/^http:.*/.test(settings.url) || /^https:.*/
        .test(settings.url))) {
        // Only send the token to relative URLs i.e. locally.
        xhr.setRequestHeader("X-XSRF-TOKEN",
          Cookies.get('XSRF-TOKEN'));
      }
    }
  }
});
````


- You can create a sticker page that has multipl;e accounts to choose from. Either Google or GitHub
- You can also have a local user database


### There are several samples building on each other, adding new features at each step:

-simple: a very basic static app with just a home page and unconditional login via Spring Boot’s OAuth 2.0 configuration properties (if you visit the home page, you will be automatically redirected to GitHub).

- click: adds an explicit link that the user has to click to login.

- logout: adds a logout link as well for authenticated users.

- two-providers: adds a second login provider so the user can choose on the home page which one to use.

- custom-error: adds an error message for unauthenticated users, and a custom authentication based on GitHub’s API.

[Resource OAuth2](https://spring.io/guides/tutorials/spring-boot-oauth2/)

