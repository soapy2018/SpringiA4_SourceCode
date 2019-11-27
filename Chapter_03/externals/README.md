运行时值注入
==================
Spring提供了两种在运行时求值的方式：

1.属性占位符

@Configuration      //表明是配置类

@PropertySource（"文件位置"）  //声明属性源

public class xx {

    @AutoWired
    
    @Enviroment env   //Enviroment会加载PropertySource对应的属性文件
    
    @bean
    
    public xxx1 ff1(){
    
        return new xxx1(
        
            env.getProperty(“属性名”)  //获取属性
            
        );
        
    }
    
...  

}
