## 开发环境

- 安装vscode https://code.visualstudio.com/

- 安装Node.js https://nodejs.org/zh-cn/

  - 最新版Node.js安装时包含了npm，无须另外安装npm

  - 安装完Node后，配置node_cache、node_global两个目录

    ``` shell
    npm config set prefix "node_global_path"
    npm config set cache "node_cache_path"
    ```

  - 最后配置镜像

    ```shell
    # 设置淘宝镜像
    # 使用cnpm名称
    npm install -g cnpm --registry=https://registry.npm.taobao.org
    
    # 或者替换官方镜像
    npm config set registry https://registry.npm.taobao.org
    
    # 切回官方
    npm config set registry https://registry.npmjs.org
    ```



## Vue开发环境配置

- 安装 @vue-cli

  ```shell
  npm install -g @vue/cli
  # check
  npm --version
  ```

  

- vue serve安装

  ```shell
  # serve 是一项http服务
  npm install -g @vue/cli-service-global
  ```

  

### vue-cli 命令

- vue create

  ```shell
  # 创建一个vue项目,-d 使用默认选项
  vue create hello-world -d
  ```

- 安装插件

  ```shell
  # element ui
  vue add element
  
  # eslint
  vue add @vue/eslint
  
  # vue router
  vue add router
  
  # vuex
  vue add vuex
  ```

  