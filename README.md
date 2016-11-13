###使用Service的Hystrix Dashboard

##### 启动Eureka Server

cd eureka-server
java -jar build/libs/eureka-server-0.0.1-SNAPSHOT.jar

##### 启动Composite Service

cd event-composite-service
java -jar build/libs/event-composite-service-0.0.1-SNAPSHOT.jar

##### 启动Review Service

cd review-service
java -jar build/libs/review-service-0.0.1-SNAPSHOT.jar

##### 访问Hystrix DashBoard

open 'http://localhost:9030/hystrix'
Input http://localhost:9030/hystrix.stream

查看当前面板的更新变化
停掉review-service，查看当前面板的更新变化

---

###使用Turbine的Hystrix Dashboard
cd turbine-server
java -jar build/libs/turbine-server-0.0.1-SNAPSHOT.jar

##### 访问Turbine的Hystrix DashBoard

open 'http://localhost:8030/hystrix'
Input http://localhost:8030/turbine.stream?cluster=default

查看当前面板的更新变化
停掉review-service，查看当前面板的更新变化

---
###在Docker中运行

```
./build.sh
docker-compose up --build
```

#####访问composite-service的Hystrix Dashboard

http://localhost:9030/hystrix/monitor?stream=http%3A%2F%2Flocalhost%3A9030%2Fhystrix.stream

#####访问Turbine的Hystrix Dashboard

http://localhost:8030/hystrix/monitor?stream=http%3A%2F%2Flocalhost%3A8030%2Fturbine.stream%3Fcluster%3Ddefault

###### 使用如下命令发送请求
http://localhost:9030/57c811115d6fe2b86380d539
http://localhost:9030/1





