```
Date : 2020 - 03 - 17

Author : Soler HO
 
Description : fiddler从安装到使用及细节问题
```
## fiddler在Ubuntu Linux上的安装

#### 安装mono
```
sudo apt-get install mono-complete
```

如果在安装过程中出现了如下的错误：
```
E: Could not get lock /var/lib/dpkg/lock-frontend - open (11: Resource temporarily unavailable)
E: Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), is another process using it?
```
截图如下：
![](./Images/ubuntu%E9%94%99%E8%AF%AF%E6%8F%90%E7%A4%BA.png)

解决方案：
```sh
sudo rm /var/lib/dpkg/lock-frontend       

sudo rm /var/lib/dpkg/lock

```

在fiddler的官网下载最新版本，下载地址：http://fiddler.wikidot.com/mono

使用命令行解压文件，然后切换到fiddler.exe文件所在的目录，使用下面命令：
```
mono fiddler.exe
```

## fiddler的工作原理
![](./Images/fiddler%E7%9A%84%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86%E5%9B%BE.png)

## fiddler的两种代理模式
#### 1.流模式（stream）
`实时`把服务器数据返回给客户端。

流模式的好处：更接近浏览器真实的行为。

#### 2.缓冲模式（buffering）
`http请求`准备好`所有数据`后，把数据`返回给客户端`。

缓冲模式的好处：可控制最后的服务器响应。

## fiddler的应用
- 安全测试
- 手机抓包测试
- 辅助定位Bug
- APP弱网模拟测试
- 抓取https的请求

## fiddler的界面介绍
#### 1.会话列表

![](./Images/fiddler%E4%BC%9A%E8%AF%9D%E5%88%97%E8%A1%A8.png)

#### 2.详情和数据统计面板

![](./Images/%E6%9F%A5%E7%9C%8B%E8%AF%B7%E6%B1%82.jpg)

2.1 Statistics：数据统计面板。性能分析。

2.2 Inspectors ：对抓到的请求进行解包，查看具体内容。

2.3 AutoResponder：文件代理【常用】。

2.4 Composer：前后端接口连调，伪造请求【常用】。

2.5 Timeline: 性能分析。对选择多个请求有意义。

#### 3.控制面板
