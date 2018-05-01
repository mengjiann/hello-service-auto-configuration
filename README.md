# Spring Custom Starter
- From Brian Clozel, and Stéphane Nicoll talk on Spring Boot auto-configuration and the conditional configuration model.
- Link to the presentation: https://www.infoq.com/presentations/spring-boot-auto-configuration

# Key takeaways
- There are two phases of how Spring Boot configure beans for an application
  - 1st phase: 
    - User annotated configuration will be given higher priority (those beans that are annotated in the application.) 
    - Annotation: @ComponentScan   
  - 2nd phase:
    - AutoConfiguration based on the included *-starter modules and also Spring Boot self opinionated configuration.
    - Annoatation: @AutoConfiguration
- Various type of @Conditional annotations that determines whether the beans should be initialised.
  - The rest of the conditions wont be processed if the higher precedence conditional failed.
  - Eg.
    - @ConditionalOnClass
    - @ConditionalOnMissingBean
    - @ConditionalOnProperty
    - @ConditionalOnExpression
- Introduction @ConfigurationProperties and @EnableConfigurationProperties on how to create beans based on properties in application properties.
- spring.factories under resources/META-INF/spring.factories.
  - EnvironmentPostProcessor -  post processing after the application context is loaded.
- ApplicationEvent lifecycle.
- Recommendation on fixing cyclic autoconfiguration problem
  - @AutoConfigureAfter and @AutoConfigureBefore
- Create customize condition by extending Spring condition
  - Create new Annotation interface
  - and condition implementation.
- Making use of -Ddebug to show the loaded beans upon starting of the application
  - or debug=true in the application.properties.
  
# Improvement
- Convert to SpringBoot 2.0 application as demostrated in the video.   