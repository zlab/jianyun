# 安装环境
## node
> 只适用于`CentOS`
### 在线安装
> node 8.x
```
curl --silent --location https://rpm.nodesource.com/setup_8.x | sudo bash -
sudo yum -y install nodejs
```

### 验证
```
node -v
npm -v
``` 

## nginx
> 复制测试环境`nginx/conf/hosts/pc.conf`过去，修改一些配置即可

# 发布流程
## 备份
> 备份后删除日志目录

## FTP上传文件
上传 `app`, `config`, `app.js`, `index.js`, `package.json`
**共两个目录，三个文件**

> 如果服务器存在`logs`, `run`, `node_modules`三个目录，删掉它们

## 修改配置文件
`config/config.prod.js`

## 安装依赖包
```
npm i --production
```

## 启动
> 启动前记得停止，以免端口被占用

```
npm start
```

## 停止
```
npm stop
```
