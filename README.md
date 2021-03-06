
## SpringCloud框架
    
    一揽子微服务开发Demo

### 父工程
    
    父工程Project空间创建完成——SpringCloudDemo
    父工程pom文件创建完成——SpringCloudDemo目录下的pom.xml文件
    
### 支付模块构建

    1、模块创建——cloud-provider-payment8001
    2、改POM——cloud-provider-payment8001根目录下的pom.xml文件
    3、写YAML——resources下的application.yaml
    4、主启动——java下的PaymentMain8001.java
    5、业务类——com.wench.springcloud包下的
                controller包下文件、dao包下文件、entities包下文件、service包下文件
                resources目录下mapper目录下文件
            
### 热部署 Devtools

    开发阶段进行热部署
    
### 消费者订单模块

    1、模块构建——cloud-consumer-order80
    2、改POM
    3、写YAML
    4、主启动
    5、业务类
    
### 工程重构

    将entities包下的通用实体体集中到一个模块中以方便调用
    构建模块——cloud-api-commons
    将entities包添加成功后，使用maven，先clean，后install
    
### EurekaServer服务端安装

    构建模块——cloud-eureka-server7001
    
### 支付微服务8001入驻EurekaServer

    cloud-provider-payment8001微服务模块下
        POM文件中添加 eureka-client 依赖坐标
        YAML文件中添加Eureka配置信息
        主启动类中添加注解 @EnableEurekaClient
        
### 订单微服务80入驻EurekaServer

    cloud-consumer-order80微服务模块下
        POM文件中添加 eureka-client 依赖坐标
        YAML文件中添加Eureka配置信息
        主启动类中添加注解 @EnableEurekaClient
        
### Eureka集群环境构建

    创建与7001类似的一个Eureka应用模块
    修改Mac的hosts文件：在末行添加域名指定语句
        localhost   eureka7001.com
        localhost   eureka7002.com
    模块名为 cloud-eureka-server7002
    
### 订单、支付俩微服务注册进Eureka集群

    修改cloud-provider-payment8001模块的YAML文件
        cloud-consumer-order80模块的YAML文件
        
### 支付微服务集群构建

    新建支付微服务模块 cloud-provider-payment8002
    
### actuator微服务信息完善

    instance-id: payment8001
    prefer-ip-address: true
    显示微服务名称及域名IP
    
### 服务发现 Discovery

    启用 discoveryClient
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    