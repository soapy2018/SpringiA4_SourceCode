环境和Profile
==================
@Configuration      //表明是配置类

public class xx {

    @Bean 
    
    @Profile(“Dev”)    //对应的 Profile激活时，相应的bean才会被创建
    
    public ff1() {...}
    
    @Bean 
    
    @Profile("Qa")  
    
    public ff2() {...}
    
    @Bean 
    
    @Profile("Prod") 
    
    public ff3() {...}
    
... }

注：Profile注解也可在类级别使用，这样的话，类中的bean只有对应的Profile激活时才会被创建
          
激活profile，用到l两个个参数spring.profiles.active和spring.profiles.default ，有多种方法来设置这两个参数：
          
1.作为DispatcherServlet的初始化参数

2.作为web应用的上下文参数

3.作为JNDI条目

4.作为环境变量

5.作为JVM的系统属性

6.在集成测试类上，使用@ActiveProfiles注解设置
