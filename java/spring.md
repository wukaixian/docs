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

  

  

  