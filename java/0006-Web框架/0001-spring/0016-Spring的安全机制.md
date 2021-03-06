Spring Security：它提供全面的安全性解决方案，同时在Web请求和方法调用处理身份确认和授权，利用依赖注入和aop技术。主要名词：
1，安全拦截器：相当应用的一把锁，能够阻止对应用程序中保护资源的访问（通常是用户名和密码 正确才能打开锁）。
2，认证管理器：通过用户名和密码来做到这点的，负责确定用户的身份。
3，访问决策管理器：根据你的身份来确定你是否拥有对资源的访问，即授权管理。
4，运行身份管理器：运行身份管理器可以用来使用另一个身份替换你的身份，从而允许你访问应用程。
序内部更深处的受保护对象。
5，调用后管理器：访问结束后还可以返回取得相关资源，其他安全管理器组件在受保护资源
被访问之前实施某种形式的安全措施强制执行，而调用后管理器则是在受保护资源被访问之后执行安全措施。
认证管理器是由org.acegisecurity.AuthenticationManager接口定义的ProviderManager是认证管理器的一个实现，它将验证身份的责任委托给一个或多个认证提供者
DaoAuthenticationProvider 是一个简单的认证提供者，它使用数据存取对象（DAO）来从关系数据库中检索用户Spring Security 支持通过LdapAuthenticationProvider 根据LDAP 进行身份验证，LdapAuthenticationProvider 是一个知道如何根据LDAP 仓库查看用户凭证的认证提供信息（包括用户的密码）。
身份验证只是Spring Security 安全保护机制中的第一步。一旦Spring Security 弄清用户的身份后，它必须决定是否允许用户访问由它保护的资源
Spring Security对Web安全性的支持大量地依赖于Servlet过滤器。这些过滤器拦截进入请求，并且在你的应用程序处理该请求之前进行某些安全处理。Spring Security 提供有若干个过滤器，它们能够拦截Servlet 请求，并将这些请求转给认证和访问决策管理器处理，从而增强安全性。