# 配置文件说明

`Goja-Framework`的主要配置文件为`application.conf`,文件格式为`Java Properties`的配置文件，文件放在`cleasses`下即可，如果是`Maven`项目的话，则在`src/main/resources`文件夹下。 例如:

```
$ tree -L 1
.
├── application.conf            # 主要配置文件
├── ehcache.xml                 # 缓存配置文件
├── shiro.ini                   # 身份授权配置文件（非必要）
└── sqlcnf                      # 存放SQL配置的文件夹
```

缓存、身份授权的配置和`ehcache`以及`apache shiro`的官方配置一致，这里就不在一一说明了。

-  `application.conf`中的配置

```
# 项目名称
app=application_name               
# 项目版本                 
app.version=0.1                       
# 项目访问地址，默认 http://127.0.0.1:8080/application_name          
domain=http://127.0.0.1:8080/application_name
# 项目视图引擎，默认为 Freemarker, 仅支持Freemarker 和 JSP，如果要设置为JSP，则app.viewtype=JSP
app.viewtype=FREE_MARKER
# 项目视图地址，默认为 /WEB-INF/views
app.viewpath=/WEB-INF/views

# 是否以开发模式启动项目，如果是开发模式，会显示请求路由、执行的SQL以及参数、freemarker的模板自动更新；默认不开启
dev.mode=true      
# 是否开启缓存，缓存框架使用的是ehcache. 默认开启                                
cache=true

# 是否开启身份验证框架，基于Apache Shiro,如果开启，那么 shiro.ini 配置文件则必须配置；默认开启
security=true

# 数据库访问地址，如果没有这个配置`db.url`的话，则不会启动配置数据库插件
db.url=jdbc:mysql://127.0.0.1:3306/
application_name?useUnicode=true&characterEncoding=utf-8
# 数据库访问用户名称
db.username=dev
# 数据库访问用户密码
db.password=dev123456
# 是否开启将SQL放在 `*-sql.xml`中配置，如果配置了，可以通过`SqlKit.sql("groupname.sqlid)`来获取执行的SQL；默认开启
db.sqlinxml=true
# 数据库连接池配置
# 初始连接池大小
db.initial.size=10
# 最小空闲连接数
db.initial.minidle=10
# 配置获取连接等待超时的时间
db.initial.maxwait=60000
# 最大活跃连接数
db.initial.active=100
# Druid 数据库监控路由地址
db.monitor=/druid/monitor

# 启动Quartz JOB
job=true

# Mongodb 服务器地址
mongo.host=127.0.0.1
# Mongodb 端口
mongo.port=20000
# MongoDB 数据库名称
mongo.db=app_mongodb
# 开启Mongo的Moriph ORM模块
mongo.moriph=true
# Mongo moriph ORM框架的实体包扫描包名
mongo.moriph.entitys=app.entitys

# Redis 插件开启，并配置远程redis的服务器地址
redis.host=127.0.0.1
# 远程redis访问端口
redis.port=5000
# redis 访问密码
redis.password=password
# redis 最大连接数
redis.maxtotal=100
# 客户端的timeout，默认5秒
redis.timeout=5000
# 配置获取连接等待超时的时间
redis.maxwait=
redis.maxidle=
redis.minidle=
# 配置连接在池中最小生存的时间
redis.minevictableidletimemillis=
redis.numtestsperevictionrun=
redis.softminevictableidletimemillis=
# 配置间隔多久才进行一次检测，检测需要关闭的空闲连接，单位是毫秒
redis.timebetweenevictionrunsmillis=60000
redis.testwhileidle=
redis.testonreturn=
redis.testonborrow=

# Goja 内部的执行线程大小数量，默认为10个
app.jobs.pool=20

# 微信插件开启，并设置微信接口地址
wx.url=http://www.xxx.com/wx/api
# 微信第三方的访问 TOKEN
wx.token=xxx
# 微信第三方的访问  secret
wx.secret=xxx
# 微信第三方的应用ID
wx.appid=xxxx

# 全文检索服务开发，并设置全文检索库的存储地址
index.path=/usr/opt/app_index
# 开启智能分词
index.smart=true

# 系统默认日志级别，默认INFO
logger=INFO
# 系统的日志文件地址，默认 ../logs/application_name.log
logger.path=../logs/application.log
# 如果需要配置自己的日志配置文件，指定改配置即可，相对classes路径
logger.config=/logback.xml

app.page=p
# 当数据查询时，每页的默认分页数量
app.page.defaultsize=10
app.page.order=direction
app.page.size=s
app.page.sort=sort

```
