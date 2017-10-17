# 说明
```
maven + springboot + mybatis + druid + oracle
```

# 搭建环境

## 安装 jdk8

## 安装 maven

## 安装 oracle jar
```
mvn install:install-file -DgroupId=com.oracle -DartifactId=ojdbc6 -Dversion=11.2.0.1.0 -Dpackaging=jar -Dfile=ojdbc6.jar
```

# 运行
```
run Application.main
```

# 配置 `application.yml`

# 开发流程
## model
建表，写一个对应的实体类，在model包下，用来返回json数据

## mapper
mybatis mapper，相当于dao层

## service
业务层，调用多个mapper完成业务逻辑

## controller
请求入口

# 发布
## 打包医生端和用户端
```
cd new 目录
mvn clean package
```

* 用户端 xinli-user/target/xinli-user-1.0.0.jar
* 医生端 xinli-dr/target/xinli-dr-1.0.0.jar

## 打包云服务
```
cd cloud-service 目录
mvn clean package
```
* 云服务 cloud-service/target/cloud-service-1.0.0.jar

# 上传
```
上传jar包到服务器： /app/appadm/xinli

-rw-r--r-- 1 appadm appadm 32772935 Oct 13 15:36 cloud-service-1.0.0.jar
-rw-r--r-- 1 appadm appadm 32772961 Oct 13 15:37 cloud-service-1.0.0.jar.bak
-rwxr-xr-x 1 appadm appadm      126 Oct 10 09:58 cloud.sh
drwxr-xr-x 8 appadm appadm     4096 Jul 22 13:11 jdk8
-rwxr-xr-x 1 root   root         20 Oct 16 15:52 pid.sh
-rw-r--r-- 1 root   root     256010 Oct 16 18:12 user.log
-rwxr-xr-x 1 appadm appadm      123 Oct  9 17:38 user.sh
-rw-r--r-- 1 appadm appadm 28032097 Oct 16 16:00 xinli-user-1.0.0.jar

```

# 运行
## 杀掉进程
```
./pid.sh
找到相应jar包到pid
kill -9 pid
```

## 运行
```
./user.sh
./dr.sh
./cloud.sh
```

## 日志
```
./user.log
./dr.log
./cloud.log
```

