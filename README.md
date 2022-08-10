# community
Open source community system: 
Based on spring boot, mybatis, mysql, redis and rabbitmq, it realizes basic registration, login, posting Comments, likes, replies, concerns, private messages, system notifications, user settings and other modules, 
while achieving website UV and dau data statistics.
## 功能简介
* 使用Spring Security 做权限控制，替代拦截器的拦截控制，并使用自己的认证方案替代Security 认证流程，使权限认证和控制更加方便灵活。
* 使用Redis的set实现点赞，zset实现关注，并使用Redis存储登录ticket和验证码，解决分布式session问题。
* 使用Redis高级数据类型HyperLogLog统计UV(Unique Visitor),使用Bitmap统计DAU(Daily Active User)。
* 使用Kafka处理发送评论、点赞和关注等系统通知，并使用事件进行封装，构建了强大的异步消息系统。
* 使用Elasticsearch做全局搜索，并通过事件封装，增加关键词高亮显示等功能。
* 对热帖排行模块，使用分布式缓存Redis和本地缓存Caffeine作为多级缓存，避免了缓存雪崩，将QPS提升了20倍(10-200)，大大提升了网站访问速度。并使用Quartz定时更新热帖排行。

## 系统建构图
![image](https://user-images.githubusercontent.com/63488829/183834262-21679adc-69c7-4987-a813-d8bcc0618eb3.png)

## 开发环境
|      技术      |           版本号            |                             官网                             |
| :------------: | :-----------------------: | :----------------------------------------------------------: |
| JDK |	 | 11 |	 https://openjdk.java.net/install/ |
| Mysql |	 | 5.7 | 	https://www.mysql.com/ |
| Redis |	 | 3.2 |	https://redis.io/download |
| Kafka |	2.3.0	 | https://kafka.apache.org/downloads |
| nginx |	1.10 |	http://nginx.org/en/download.html |
