# Spring Security : 

### Authentication : 

We use AuthenticationManager interface for the authentication and this interface has one method which is authenticate(Authentication authentication) , this methods will : 

        public interface AuthenticationManager {

          Authentication authenticate(Authentication authentication)
            throws AuthenticationException;
        }

* return an Authentication if authenticated=true  
* Throw an AuthenticationException if it believes that the input represents an invalid principal. 
* Return null if it cannot decide.

ProviderManager is mostly implement AuthenticationManager , and ProviderManager has a chain of AuthenticationProvider instances. 
 
        public interface AuthenticationProvider {

          Authentication authenticate(Authentication authentication)
              throws AuthenticationException;

          boolean supports(Class<?> authentication);
        }


we can also customize the configuration , amd we will use the AuthenticationManagerBuilder , which is great for setting up in-memory, JDBC, or LDAP user details or for adding a custom UserDetailsService.

The following example shows an application that configures the global (parent) AuthenticationManager:

        @Configuration
        public class ApplicationSecurity extends WebSecurityConfigurerAdapter {

          ... // web stuff here

          @Autowired
          public void initialize(AuthenticationManagerBuilder builder, DataSource dataSource) {
            builder.jdbcAuthentication().dataSource(dataSource).withUser("dave")
              .password("secret").roles("USER");
          }

        }



### Authorization :

for the authorization there are three implementations provided by the framework and all three delegate to a chain of AccessDecisionVoter instances, a bit like the ProviderManager delegates to AuthenticationProviders.

Example : 

        boolean supports(ConfigAttribute attribute);

        boolean supports(Class<?> clazz);

        int vote(Authentication authentication, S object,
                Collection<ConfigAttribute> attributes);



### Request Matching for Dispatch and Authorization :

A security filter chain (or, equivalently, a WebSecurityConfigurerAdapter) has a request matcher that is used to decide whether to apply it to an HTTP request. Once the decision is made to apply a particular filter chain, no others are applied. However, within a filter chain, you can have more fine-grained control of authorization by setting additional matchers in the HttpSecurity configurer, as follows:

        @Configuration
        @Order(SecurityProperties.BASIC_AUTH_ORDER - 10)
        public class ApplicationConfigurerAdapter extends WebSecurityConfigurerAdapter {
          @Override
          protected void configure(HttpSecurity http) throws Exception {
            http.antMatcher("/match1/**")
              .authorizeRequests()
                .antMatchers("/match1/user").hasRole("USER")
                .antMatchers("/match1/spam").hasRole("SPAM")
                .anyRequest().isAuthenticated();
          }
        }



# Spring Security Cheat Sheet : 



## Step 1: set up a user model and repo

## Step 2: create a controller for that model

## Step 3: UserDetailsServiceImpl implements UserDetailsService

gets a User from the database by username (make sure your repository has the method to make this easy!)

## Step 4: ApplicationUser implements UserDetails

use IntelliJ to implement the methods; make the boolean ones all return true

## Step 5: WebSecurityConfig extends WebSecurityConfigurerAdapter

- has a UserDetailsService
- passwordEncoder bean
- configure AuthManagerBuilder
    - `auth.userDetailsService(userDetailsService).passwordEncoder(passwordEncoder());`
- configure HttpSecurity
    - cors? csrf?
    - matchers for URLs that are allowed
        - ensure that login and signup URLs allowed; also consider homepage etc.
    - formLogin with login page set up
    - logout

```
    @Override
    @Bean
    public AuthenticationManager authenticationManagerBean() throws Exception {
        return super.authenticationManagerBean();
    }
```

## Step 6: registration page
- create it w/ form
- ensure it posts to a route your controller is ready for
- check it's saving in the DB
```
    // maybe autologin?
    Authentication authentication = new UsernamePasswordAuthenticationToken(newUser, null, new ArrayList<>());
    SecurityContextHolder.getContext().setAuthentication(authentication);
```

## Step 7: login page
- create it w/ form
- ensure it posts to the route you specified in web config
- try it out!
- add to a template w/ things about the Principal
