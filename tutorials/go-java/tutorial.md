# Dubbogo go-java 互通案例

## 教程说明

通过该教程，你将会：

* 使用 dubbo-go 框架开启简单RPC服务
* 并完成go-java的客户端和服务端之间的调用示例。

案例学习时间预计15分钟左右。

点击右下角的"下一步"按钮继续。

## 准备工作

本节你将通过过 git 命令下载代码，并启动 zookeeper 注册中心

### 获取客户端及服务端代码

请使用下面的命令获取客户端及服务端代码

```bash
git clone https://github.com/apache/dubbo-go-samples.git
cd general/dubbo/
```

### 启动 zookeeper

通过如下命令启动 zookeeper

```bash
sh ~/prepare.sh
```

## 运行程序

本节，你将使用 go 命令来运行上述的代码和配置

### 启动服务端

1. 开启新 console 窗口：<br>
   <tutorial-terminal-open-tab name="服务端">点击我打开</tutorial-terminal-open-tab>

2. 在新窗口中执行命令，进入cmd目录

```bash
cd dubbo-go/go-server/cmd
```

指定配置文件, 启动服务端

```bash
export CONF_PROVIDER_FILE_PATH=../conf/server.yml && export GOPROXY=https://goproxy.io,direct && go run .
```

看到下面的反馈则表示启动成功<br>

```
 nacos/registry.go:200   update begin, service event: ServiceEvent{Action{add}, Path{dubbo...
```


### 启动客户端

1. 开启新 console 窗口：<br>
   <tutorial-terminal-open-tab name="客户端">点击我打开</tutorial-terminal-open-tab>

2. 在新窗口中执行命令

```bash
cd dubbo-go/go-client/cmd
```


指定配置文件, 启动客户端

```bash
export CONF_CONSUMER_FILE_PATH=../conf/client.yml && export GOPROXY=https://goproxy.io,direct && go run .
```

看到下面的反馈则表示调用成功<br>

```
[2021-03-04/05:53:34 main.main: client.go: 64] response result: &{A001 Alex Stocks 18 2021-03-04 05:53:34.253 +0000 UTC}
```

dubbo-go 初体验完成～