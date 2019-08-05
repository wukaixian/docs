### 一、名词定义

1. **Third-party application** 第三方应用程序，也称为客户端，如APP、SPA客户端、WEB客户端

2. **HTTP Service HTTP** 服务提供商，即服务器端

3. **Resource Owner** 资源所有者

4. **User Agent** 用户代理，如浏览器

5. **Authorization server** 认证服务，IdentityServer

6. **Resource Server** 资源服务器，资源保存的地方

   

### 二、OAuth 思路

OAuth在"客户端"与"服务提供商"之间，设置了一个授权层（authorization layer）。"客户端"不能直接登录"服务提供商"，只能登录授权层，以此将用户与客户端区分开来。"客户端"登录授权层所用的令牌（token），与用户的密码不同。用户可以在登录的时候，指定授权层令牌的权限范围和有效期。

"客户端"登录授权层以后，"服务提供商"根据令牌的权限范围和有效期，向"客户端"开放用户储存的资料。



### 三、运行流程

![flow](D:\Github\docs\.net\IdentityServer4\flow.png)

A.用户打开客户端以后，客户端要求用户给予授权

B.用户同意给予客户端授权

C.客户端用上一步获得的授权，向认证服务器申请令牌（**access_token**）

D.认证服务器对客户端进行认证后，确认无误，同意发放令牌（**access_token**）

E.客户端使用令牌，向资源服务器申请获得资源

F.资源服务器确认令牌无误，同意向客户端开放资源

### 四、客户端授权模式

* 授权码模式（**authorization code**）
* 简化模式（**implicit**）
* 密码模式 （**resource owner password credntials**）
* 客户端模式（**client credentials**）



### 五、授权码模式

授权码模式（authorization code）是功能最完整、流程最严密的授权模式。它的特点就是通过客户端的后台服务器，与"服务提供商"的认证服务器进行互动。

![authoriztion code flow](D:\Github\docs\.net\IdentityServer4\authoriztion_code.png)

它的步骤如下：

1. 用户访问客户端，后者将前者导向认证服务器
2. 用户选择是否给予客户端授权
3. 假设用户给予授权，认证服务器将用户导向客户端事先指定的重定向uri，同时附上一个授权码
4. 客户端收到授权码，附上早先的重定向uri，向认证服务器申请令牌。这一步是客户端后台的服务器上完成的，对用户不可见
5. 认证服务器核对了授权码和重定向URI，确认无误后，向客户端发送访问令牌（**access token**）和更新令牌（**refresh token**）

这些步所需要的参数：

1. **response_type** 授权类型，必选项，此处的值固定为”**code**" (授权码模式下)
2. **client_id ** 客户端ID，必选项
3. **redirect_uri** 重定向URI，可选项
4. **scope ** 申请的权限范围，可选项
5. **state** 客户端当前状态，可以指定任意值，认证服务器会原封不动地返回这个值

一个示例

```http
GET /authorize?response_type=code&client_id=s6BhdRkqt3&state=xyz
        &redirect_uri=https://wwww.example.com/callback.html
```

第3步中，服务器回应客户端的URI，包含以下参数：

* **code** 授权码，必选项，code的有效期应该很短，通常设为10分钟，客户端只能使用该码一次，重复使用会被授权服务器拒绝，code与客户端ID和重定向URI，是一一对应的关系
* **state** 如果客户端的请求中包含这个参数，认证服务器必须一模一样包含这个参数

一个示例

```http
HTTP/1.1 302 Found
Location: https://wwww.example.com/callback?code=SplxlOBeZQQYbYS6WxSbIA
          &state=xyz
```

第4步中，客户端向认证服务器申请令牌的HTTP请求中，包含以下参数：

* **grant_code** 表示使用的授权模式，必选项，此处固定值为“**authoriztion_code**”
* **code** 表示上一步获得的授权码，必选项
* **redirect_uri ** 表示重定向URI，必选项，且必须跟步骤1中的值保持一致
* **client_id** 表示客户端ID，必选项

一个例子：

```http
POST /token HTTP/1.1
Host: server.example.com
Authorization: Basic czZCaGRSa3F0MzpnWDFmQmF0M2JW
Content-Type: application/x-www-form-urlencoded

grant_type=authorization_code&code=SplxlOBeZQQYbYS6WxSbIA
&redirect_uri=https://www.example.com&client_id=?
```



第5步中，认证服务器返回的参数，包括：

* **access_token** 表示访问令牌，required
* **token_type** 表示令牌类型，bearer或mac类型，required
* **expires_in** 表示过期时间，单位为秒
* **refresh_token** 更新令牌，用来获取下一次的访问令牌，not required
* **scope** 权限范围，可忽略

示例：

```http
    HTTP/1.1 200 OK
     Content-Type: application/json;charset=UTF-8
     Cache-Control: no-store
     Pragma: no-cache

     {
       "access_token":"2YotnFZFEjr1zCsicMWpAA",
       "token_type":"bearer",
       "expires_in":3600,
       "refresh_token":"tGzv3JOkF0XG5Qx2TlKWIA",
       "example_parameter":"example_value"
     }
```



### 六、简化模式

简化模式（implicit grant type）不通过第三方应用程序的服务器，直接在浏览器中向认证服务器申请令牌，跳过了"授权码"这个步骤，因此得名。所有步骤在浏览器中完成，令牌对访问者是可见的，且客户端不需要认证。

![implicit mode](D:\Github\docs\.net\IdentityServer4\implicit_mode.png)



步骤如下：

```html
（A）客户端将用户导向认证服务器。

（B）用户决定是否给于客户端授权。

（C）假设用户给予授权，认证服务器将用户导向客户端指定的"重定向URI"，并在URI的Hash部分包含了访问令牌。

（D）浏览器向资源服务器发出请求，其中不包括上一步收到的Hash值。

（E）资源服务器返回一个网页，其中包含的代码可以获取Hash值中的令牌。

（F）浏览器执行上一步获得的脚本，提取出令牌。

（G）浏览器将令牌发给客户端。
```



[详细查询>>](http://www.ruanyifeng.com/blog/2014/05/oauth_2_0.html)

