# TODO
 - Spring Security blocked h2 console.

```              
http.authorizeRequests()
  .antMatchers("/h2-console/**").hasRole("ADMIN") //allow h2 console access to admins only
  .anyRequest().authenticated() //all other urls can be access by any authenticated role
  .and().formLogin() //enable form login instead of basic login
  .and().csrf().ignoringAntMatchers("/h2-console/**") //don't apply CSRF protection to /h2-console
  .and().headers().frameOptions().sameOrigin(); //allow use of frame to same origin urls
```

- implement liquibase