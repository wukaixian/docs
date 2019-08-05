### 关键点

1. 开发环境只安装JDK即可，JDK包括了编译器和虚拟机，JRE是服务器上的运行环境，没有编译器，SDK是一个过时的名称，Java SE表示标准版本
2. Window环境安装的时候路径不要有空格，安装完成了将路径配置到PATH中，不要配置CLASSPATH
3. 文件名与public类名要一致，区分大小写，否则无法编译通过
4. java中用final声明常量，习惯上使用全大写命名，类常量使用static final声明
5. 同时const也是保留字，但还没有被使用
6. ==不能用于比较字符串是否相等，==只是判断引用是否一致，并不是值是否一样，所以应该使用equals来比较
7. java中的foreach:  for(variable:collection) statement
8. 