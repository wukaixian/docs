## Developer Tools

Spring Boot提供了一些工具，使得整个开发体验更加令人愉快。

`spring-boot-devtools`模块可以包含在任何项目中，提供额外的开发工具支持。

```xml
<!--添加dev-tools模块引用-->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-devtools</artifactId>
    <optional>true</optional>
</dependency>
```

dev-tools引入后，默认情况下，一切都是自动的。开发工具会随着项目的<span style="color:red">**重新编译**</span>（package）而自动重启（热切换）。

在开发环境上，dev-tools是默认禁用的，因此部署到生产环境时，不用手动移除开发工具，让它自己自动化管理就好了。



## 禁用生动重启

``` shell
# propperties中配置禁用自动重启
spring.devtools.restart.enabled=false
```

