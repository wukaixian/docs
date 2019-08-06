## 常用 Shell

```shell
# find file
find [basePath] -name fileName
# find file ignoreCase
find [basePath] -iname fileName

# modify permission
chmod 744 fileName

# su=swtich user
su userName

# uname:display system relate information
uname -a

# df:dist space free
# 查看文件系统中磁盘的使用情况
df

# top 默认按cpu占用情况排序，显示占用量比较大的进程
top [-u]

# *.tar file unpack
tar -xvf fileName.tar  #tar文件非压缩文件，只是打包文件（将多个文件包装为一个文件）

```



### 网络相关shell

```shell
# 查看所有网络接口（网卡信息）
ifconfig

# 查看tcp连接 t:tcp 端口 n:
netstat -tunlp
```





