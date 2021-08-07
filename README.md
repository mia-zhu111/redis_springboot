# redis_springboot
redis与springboot：
1）导入依赖
2）配置applicapplication.properties
3)添加redis配置类 config包下
4）controller包下写testcontroller

【注】redis中testController 添加注解@RestController
      需要web页面，所以引入web启动器，在test中添加@RequestMapping注解

错误1：
Maven Repository: import com.fasterxml.jackson.datatype.joda.cfg.
解决1：
添加关于joda的依赖
  <dependency>
            <groupId>com.fasterxml.jackson.datatype</groupId>
            <artifactId>jackson-datatype-joda</artifactId>
            <version>2.0.4</version>
        </dependency>

        <!-- Extends Jackson mapper; but also needs annotations slightly,
     to support JsonFormat-->
        <dependency>
            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-annotations</artifactId>
        </dependency>
        <dependency>
            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-core</artifactId>
        </dependency>
        <dependency>
            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-databind</artifactId>
        </dependency>

        <!-- And obviously also depends on Joda lib -->
        <dependency>
            <groupId>joda-time</groupId>
            <artifactId>joda-time</artifactId>
            <!-- Baseline was 2.2 for Jackson 2.4: no new functionality used from laster
                 versions but gradually increasing baseline to get bugfixes etc
                 2.7 for Jackson 2.9
                 2.9[.9] for Jackson 2.10+
              -->
            <version>2.10.8</version>
        </dependency>

错误2：
java.net.ConnectException: Connection refused  
解决2:
在中断redis-service开启redis
