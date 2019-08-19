## spring boot 记录

* response日期格式化

  ```java
  // 通过spring配置统一时间格式
  spring.jackson.date-format=yyyy-MM-dd
  
  // 通过注解指定格式
  @JsonFormat(pattern="yyyy-MM-dd HH:mm:ss")
  private Date date;
  ```

* jpa mysql配置

  ```yaml
  # 数据库地址
  spring.datasource.url=jdbc:mysql://127.0.0.1:3306/test?serverTimezone=UTC&useSSL=false
  
  # 用户&密码
  spring.datasource.username=root
  spring.datasource.password=123456
  
  # 数据驱动
  spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
  
  # 依赖mysql jar包
  dependency:
  	groupId: mysql
  	artifactId: mysql-connector-java
  
  # jpa jar包
  dependency:
  	groupId: org.springframeword.boot
  	artifactId: spring-boot-starter-data-jpa
  
  # 泛型仓储
  ... extends JpaRepository<TEntity,TIdentity>
  
  ```

* RestController

  ```java
  // url参数
  @RequestMappint(value="/{id}")
  public ResponseEntity action (@Pathvariable int id){}
  
  // body参数
  @RequestBody
  
  // http method
  RequestMethod.Delete | Put | Post | Get ...
  ```

* Logging config

  spring boot本身可能已经包含了logback日志模块，所以一般不需要额外添加依赖引用，按需要配置日志即可

  ```xml
  <!--日志依赖组件（可能包含在其他jar包的传递依赖中）-->
  <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-logging</artifactId>
  </dependency>
  
  <!--日志配置-->
  <configuration>
      <!--日志保存位置（项目根目录下logs文件夹）-->
      <property name="LogPath" value="./logs"/>
      <!--控制台输入配置-->
      <appender name="Console"
                class="ch.qos.logback.core.ConsoleAppender">
          <layout class="ch.qos.logback.classic.PatternLayout">
              <Pattern>
                  %black(%d{ISO8601}) %highlight(%-5level) [%blue(%t)] %yellow(%C{1.}): %msg%n%throwable
              </Pattern>
          </layout>
      </appender>
      <!--文件输出配置-->
      <appender name="RollingFile"
                class="ch.qos.logback.core.rolling.RollingFileAppender">
          <!--输出的文件名-->
          <file>${LogPath}/spring-boot-logger.log</file>
          <encoder
                  class="ch.qos.logback.classic.encoder.PatternLayoutEncoder">
              <Pattern>%d %p %C{1.} [%t] %m%n</Pattern>
          </encoder>
          <rollingPolicy
                  class="ch.qos.logback.core.rolling.TimeBasedRollingPolicy">
              <!-- rollover daily and when the file reaches 10 MegaBytes -->
              <fileNamePattern>${LOGS}/archived/spring-boot-logger-%d{yyyy-MM-dd}.%i.log
              </fileNamePattern>
              <timeBasedFileNamingAndTriggeringPolicy
                      class="ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP">
                  <maxFileSize>10MB</maxFileSize>
              </timeBasedFileNamingAndTriggeringPolicy>
          </rollingPolicy>
      </appender>
      <root level="warn">
          <appender-ref ref="RollingFile"/>
          <appender-ref ref="Console"/>
      </root>
      <logger name="com.example.one.controller" level="warn" additivity="false">
          <appender-ref ref="RollingFile"/>
          <appender-ref ref="Console"/>
      </logger>
  </configuration>
  ```

  

  