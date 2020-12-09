# This is a forked repo for practicing Spring Boot testing

# Notes

- ## Features of Spring Boot
    - Spring Boot is an opinionated framework used to create Spring Framework applications quickly
    - Provides curated dependencies with version management
    - Provides starter dependencies for common features
        - ex. Spring Data JPA starter includes:
            - Spring Data JPA, Hibernate, HikariCP, Spring JDBC, etc.
    - Provides opinionated auto-configuration of included features.
        - ex. when H2 database is included, Spring Boot will auto-configure a H2 in-memory database
        
- ## Spring Boot Testing

    - Spring Boot Test features are enabled through the inclusion of the starter:
        - spring-boot-starter-test
    - This starter provides:
        - common testing dependencies
        - Spring Boot Testing Dependencies - (testing annotations and support)
        - Spring Boot Testing Auto-Configuration
        
- ## Spring Boot Test Scope Dependencies
    - The Spring Boot Test (as of version 2.1.x) starter brings in the following Testing libraries:
        - #### JUnit 
            - (Spring Boot 2.1 and earlier is JUnit4, Spring Boot 2.2+ will support Junit 5)
        - #### Spring Test 
            - Spring Framework Testing features
        - #### AssertJ 
            - Fluent assertions
        - #### Hamcrest 
            - Matchers for testing
        - #### Mockito 
            - Mocking framework
        - #### JSONAssert 
            - Assertions for JSON
        - #### JsonPath 
            - XPath for JSON
            
- ## Spring Testing Context with Spring Boot
    - #### @SpringBootTest
        - will enable Spring Context
    - If using Junit 4 the following class level annotation is also required:
        - @RunWith(SpringRunner.class)
    - Annotation includes @ExtendWith(SpringExtension.class), thus not needed
    - By default, searches for @SpringBootConfiguration
        - included with @SpringBootApplication
    - By default, Spring Boot will not start a web browser
    
    
- ## Web Environment
    - #### @SpringBootTest(webEnvironment= <option>)
        - enables the web environment
    - Web Environment Options:
        - #### MOCK
            - Default - loads mock web environment
        - #### RANDOM_PORT
            - Provides embedded web sever listening on a random port
            - Useful to avoid port conflicts
        - #### DEFINED_PORT
            - Provides embedded web server listening on a 8080 (default) or server.port defined in application.properties
        - #### NONE
            - No Web Environment
            
- ## Spring Boot Test Annotations
    - #### @TestComponent
        - Stereotype for test components
    - #### @TestConfiguration
        - Java Configuration for tests
    - #### @LocalServerPort
        - Inject port of running server
    - #### @MockBean
        - Inject Mockito Mock
    - #### @MockSpy
        - Inject Mockito Spy
        
- ## Spring Boot Test Slices
    - #### @SpringBootTest
        - will by default scan your project and bring up a full context using all available (enabled) auto configurations
            - This can be heavy and costly on more complex applications
    - #### Test Slices
        - targeted lightweight configurations which do not enable the complete defined auto configuration
        - Ex. @JsonTest - creates a Spring Boot configured JSON environment for Jackson (default) or Gson
        - User @...Test on test class instead of @SpringBootTest
        - ##### List of Common Test Slices:
            - ##### @DataJdbcTest
            - ##### @DataJpaTest
            - ##### @DataLdapTest
            - ##### @DataMongoTest
            - ##### @DataNeo4jTest
            - ##### @DataRedisTest
            - ##### @jdbcTest
            - ##### @JooqTest
            - ##### @JsonTest
            - ##### @RestClientTest
            - ##### @WebFluxTest
            - ##### @WebMvcTest
        






# Testing Spring Boot B2G - SFG Brewery

All source code examples in the repository are for my [Online Course - Testing Spring Beginner to Guru](https://www.udemy.com/testing-spring-boot-beginner-to-guru/?couponCode=GITHUB_REPO)

This source code repository contains JUnit 5 and Spring Framework Testing examples.

## Setup
### Requirements
* Should use Java 11 or higher. Previous versions of Java are un-tested.
* Use Maven 3.6.0 or higher

## Support
For questions and help:
* Please post in course
* Or post in the Slack Community exclusive to the course.

GitHub Issues will not be addressed.
