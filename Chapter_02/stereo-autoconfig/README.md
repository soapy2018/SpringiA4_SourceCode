自动装配
==================
1.配置类中开启自动扫描，参看类CDPlayerConfig
@Configuration       //表明是配置类
@ComponentScan      /*启用组件自动扫描（可指定扫描路径），默认扫描该类路径及子路径下的@Component注解类，并为其创建bean */
public class xx {...}

2.定义组件类，使其可被发现并自动创建，参看类CDPlayer和SgtPeppers
@Component        //表明该类为组件类，需要spring自动为其创建bean
public class xx {...}

3.自动装配依赖的bean，参看类CDPlayer构造函数CDPlayer()
public class xx {
    @Autowired      //用在任何方法上，spring会为方法自动装配依赖的bean，若找不到依赖的bean或有多于一个满足的bean都会报错，该注解与@Inject类似
    public ff() {...}
 ... }
