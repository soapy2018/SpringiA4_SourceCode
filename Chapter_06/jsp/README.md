使用Thymeleaf
==================
Thymeleaf没有与Servlet规范耦合，因此Thymeleaf能进入JSP所无法涉足的领域。

要在Spring中使用Thymeleaf，我们需要配置三个启用Thymeleaf与Spring集成的bean，java配置参考例子中类WebConfig：

ThymeleafViewResolver：将逻辑视图名称解析为Thymeleaf模板视图

SpringTemplateEngine：处理模板并渲染结果

TemplateResolver：加载Thymeleaf模板

