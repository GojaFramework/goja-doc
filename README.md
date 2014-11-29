# Gaja 介绍

`Goja`是在 [@JFinal](http://www.jfinal.com) 框架的基础上，以及 [@JFinal-ext](http://git.oschina.net/zhouleib1412/jfinal-ext) 的扩展补充，同时参考`Play 1.2`系列的方式， 以`COC`(约定纪配置)的原则，在各个项目的开发中对使用场景的不断积累的一个快速、高效的web开发框架。

主要特点如下：

1. 在 `JFinal`基础上，参考`Play 1.2`配置方式，将大部分的配置整合到一个配置文件，并支持动态启动相关插件等；
2. 需要使用`JDK-1.6` 以及 支持`Servlet 3.0`以上版本的Web容器；
3. 通过`javax.servlet.ServletContainerInitializer`(需要`Servlet3.0`以上容器)的方式去掉了`web.xml`的配置；
4. 通过`goja-cli`工具支持那些不使用`Maven`的开发人员；
5. 整合`job`、`mongodb`、`shiro`、`redis`等常用插件；
6. 大量`WEB`开发中，常用的功能脚手架程序，比如： excel处理、文件上传处理、登录授权功能处理等；
7. 集成常用的工具包比如`Google Guava`等，并使用常用函数的示例；
8. 路由 COC、Model COC、Controller COC等；
9. `Freemarker` 支持 模版 继承，部分常用的标签等；
10. 测试自动执行`misc/sql`目录下的`sql`文件，默认按照文件名字母数字排序依次执行；
11. 支持测试框架的使用
