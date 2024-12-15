# Spring Boot 2 + Angular 10: User Registration and Login using JWT Authentication, OAuth2 Social Login with Facebook, Google, LinkedIn, and Github using Spring Security 5 and Two Factor Authentication (2FA)

[Creating Backend - Spring REST API - Part 1](https://www.javachinna.com/spring-boot-angular-10-user-registration-oauth2-social-login-part-1/)

[Creating Backend - Spring REST API - Part 2](https://www.javachinna.com/2020/10/23/spring-boot-angular-10-user-registration-oauth2-social-login-part-2/)

[Creating Angular 10 Client Application - Part 3](https://www.javachinna.com/2020/10/28/spring-boot-angular-10-user-registration-oauth2-social-login-part-3/)

[Secure Spring Boot Angular Application with Two Factor Authentication](https://www.javachinna.com/spring-boot-angular-two-factor-authentication/)

[Dockerize Angular with NGINX and Spring Boot with MySQL using Docker Compose](https://www.javachinna.com/angular-nginx-spring-boot-mysql-docker-compose/)


## src/main/resources/application.properties

# Database configuration props
spring.datasource.url=jdbc:mysql://localhost:3306/demo?createDatabaseIfNotExist=true&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=1234
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# Hibernate props
spring.jpa.show-sql=true
#spring.jpa.hibernate.ddl-auto=none
spring.jpa.hibernate.ddl-auto=create
spring.jpa.properties.hibernate.dialect = org.hibernate.dialect.MySQL5InnoDBDialect

# Social login provider props
spring.security.oauth2.client.registration.google.clientId=539628264530-29b5fpedi5p0svu4m5cunon5iekg6m96.apps.googleusercontent.com
spring.security.oauth2.client.registration.google.clientSecret=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
spring.security.oauth2.client.registration.facebook.clientId=<your-client-id>
spring.security.oauth2.client.registration.facebook.clientSecret=<your-client-secret>
spring.security.oauth2.client.provider.facebook.user-info-uri=https://graph.facebook.com/me?fields=id,name,email,picture
spring.security.oauth2.client.registration.github.clientId=<your-client-id>
spring.security.oauth2.client.registration.github.clientSecret=<your-client-secret>
spring.security.oauth2.client.registration.linkedin.clientId=<your-client-id>
spring.security.oauth2.client.registration.linkedin.clientSecret=<your-client-secret>
spring.security.oauth2.client.registration.linkedin.client-authentication-method=post
spring.security.oauth2.client.registration.linkedin.authorization-grant-type=authorization_code
spring.security.oauth2.client.registration.linkedin.scope=r_liteprofile, r_emailaddress
spring.security.oauth2.client.registration.linkedin.redirect-uri={baseUrl}/login/oauth2/code/{registrationId}
spring.security.oauth2.client.registration.linkedin.client-name=Linkedin
spring.security.oauth2.client.registration.linkedin.provider=linkedin
spring.security.oauth2.client.provider.linkedin.authorization-uri=https://www.linkedin.com/oauth/v2/authorization
spring.security.oauth2.client.provider.linkedin.token-uri=https://www.linkedin.com/oauth/v2/accessToken
spring.security.oauth2.client.provider.linkedin.user-info-uri=https://api.linkedin.com/v2/me
spring.security.oauth2.client.provider.linkedin.user-name-attribute=id
linkedin.email-address-uri=https://api.linkedin.com/v2/emailAddress?q=members&projection=(elements*(handle~))

app.auth.tokenSecret=926D96C90030DD58429D2751AC1BDBBC
app.auth.tokenExpirationMsec=864000000
    # After successfully authenticating with the OAuth2 Provider,
    # we'll be generating an auth token for the user and sending the token to the
    # redirectUri mentioned by the frontend client in the /oauth2/authorization request.
    # We're not using cookies because they won't work well in mobile clients.
app.oauth2.authorizedRedirectUris=http://localhost:8081/oauth2/redirect,myandroidapp://oauth2/redirect,myiosapp://oauth2/redirect
# For detailed logging during development
#logging.level.com=TRACE
logging.level.org.springframework=INFO
#logging.level.org.hibernate.SQL=TRACE
#logging.level.org.hibernate.type=TRACE
