## 关键点

1. 开发环境只安装JDK即可，JDK包括了编译器和虚拟机，JRE是服务器上的运行环境，没有编译器，SDK是一个过时的名称，Java SE表示标准版本
2. Window环境安装的时候路径不要有空格，安装完成了将路径配置到PATH中，不要配置CLASSPATH
3. 文件名与public类名要一致，区分大小写，否则无法编译通过
4. java中用final声明常量，习惯上使用全大写命名，类常量使用static final声明
5. 同时const也是保留字，但还没有被使用
6. ==不能用于比较字符串是否相等，==只是判断引用是否一致，并不是值是否一样，所以应该使用equals来比较
7. java中的foreach:  for(variable:collection) statement



## 设置

* 设置console输出颜色

  ```java
  // color enum define
  public enum Color {
      RED("\u001B[30m"),
      YELLOW("\u001B[33m"),
      BLUE("\u001B[34m"),
      PURPLE("\u001B[35m"),
      WHITE("\u001B[37m"),
      GREEN("\u001B[32m"),
      RESET("\u001B[0m");
      private final String code;
      Color(String code) {
          this.code = code;
      }
      
      @Override
      public String toString() {
          return code;
      }
  }
  
  // use console color
  public class Main(){
      static{
          // 设置输出颜色
          System.out.println(Color.YELLOW);
      }
  }
  ```

  

## 语言版本问题

* ctrl+shift+alt+s 打开项目设置，设置模块语言版本
* 如果是maven项目，设置maven的编译插件

``` xml
<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>3.6.1</version>
            <configuration>
                <source>12</source>
                <target>12</target>
            </configuration>
        </plugin>
    </plugins>
</build>
```

