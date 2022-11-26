# Fix IntelliJ Spring Boot Maven spring-boot-devtools Auto Restart. 

Our application wasnt restarting after changes were made. We had to click to  build and run everytime we made a simple change.
which was fustrating & time wasting, or even worst sometimes one forgets to restart the server, and gets stuck debugiing changes that wernt there.

So, I had to solve this issue. this solution worked for me. InshaAllah will work for you too.


## 1- Updated pom.xml spring-boot-devtools dependency.

```xml
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-devtools</artifactId>
   <optional>true</optional>
   <scope>runtime</scope>
</dependency>
```

## 2- Add this configurat to your local development profile(we are using .yml in our case)

Choose the Interval that suits you. or you can disable it.

```yml
spring:
  devtools:
    restart:
      enabled: true
      pollInterval: 1s
```

## 3- Configure your IntelliJ IDE.

   1. Go to File -> Settings –> Build, Execution, Deployment –> Compiler. & Enable: "Build project automatically".
   2. Go to File -> Settings –> Advance Settings -> Compiler. & Enable "Allow auto-make to start even if developed application is currently running".
