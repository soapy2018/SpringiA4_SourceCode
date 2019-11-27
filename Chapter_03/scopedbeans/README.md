bean作用域
==================
代理可以解决函数增强问题，例如多个类实现了同一个接口，现在需要增强接口的A方法，假如不用代理需要修改所有类，而使用静态代理，可以写一个代理类实现接口，并对方法A进行增强，若有多个方法需要增强，此时静态代理就会有问题，需要修改每个方法进行增强，但是动态代理就不需要，动态代理可以在运行时知道哪个方法在调用进而进行增强，就不需要指定加强哪个具体方法，动态代理只能针对接口，若不是接口则用CGLIIB生成代理


bean的作用域包括：

1.单例（Singleton）：在整个应用中只创建bean的一个实例

2.原型（Prototype）：每次注入或者通过spring上下文获取时都会创建一个新的实例

3.会话（Session）：web应用中，为每一个会话创建一个bean实例

4.请求（Request）：web应用中，为每一个请求创建一个bean实例              

单例是默认作用域，可用如下方法改变：

@Bean 或者 @Component

@Scope(ConfigurableBeanFactory.SCOPE_PROTOTYPE)     //原型

方法

@Bean 或者 @Component

@Scope(
        
        value=WebApplicationContext.SCOPE_SESSION,     //会话 
        
        //value=WebApplicationContext.SCOPE_REQUEST   //请求
        
        proxyMode=ScopedProxyMode.INTERFACES)        /* 当需要将会话或者请求作用域的bean注入单例bean时，此属性表示用动态代理注入，Spring会注入一个bean的代理，此时bean是接口类型 */
        
        //proxyMode=ScopedProxyMode.TARGET_CLASS   //如果bean类型是具体类的话，用CGLIB生成基于类的代理    
）

方法

动态代理示意图：

