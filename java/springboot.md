## 配置

- Run之后马上退出 `SpringBoot Process finished with exit code 0`

  ```xml
  <!--原因：缺少依赖项，在pom.xml文件中添加以下依赖-->
  <dependency>
     <groupId>org.springframework.boot</groupId>
     <artifactId>spring-boot-starter-web</artifactId>
  </dependency>
  ```

- Ioc找不到bean问题

  ```java
  // 1.在实现类中添加@Component注解
  @Component
  public class ServiceImpl implements Service{
      
  }
  
  // 2.在接口添加@Service注解
  @Service
  public interface Service{
      
  }
  ```





## 项目构建

