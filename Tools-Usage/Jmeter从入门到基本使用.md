## 几个测试术语
- Performance Test （性能测试）
- Load Test （负载测试）
- Stress Test （压力测试）
## Jmeter概述
#### 1.什么是Jmeter？
- 多线程框架 - 支持多并发操作
- 用于对服务器模拟负载
- 支持web、数据库、FTP服务器系统的性能测试
- 开源、纯Java、可以进行二次开发。
- 可以在任何接受Java虚拟机的环境/工作站上运行

JMeter是一个Java桌面应用程序，具有使用Swing图形API的图形界面。
#### Jmeter的功能
- 开源免费
- 简单直观的GUI
- 多线程框架允许多个线程进行并发采样，并通过单独的线程组同时对不同函数进行采样。
- 具有扩展性
- 可用于执行应用程序的自动和功能测试。

## Jmeter的工作原理
JMeter模拟一组用户向目标服务器发送请求，并通过表，图表等返回显示目标服务器/应用程序的性能/功能的统计信息。

![](https://github.com/SolerHo/Software-Testing/blob/master/Tools-Usage/Images/Jmeter%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86%E5%9B%BE.png)

## Jmeter的应用
- 可以用于测试静态或者动态资源的性能（文件、Servlets、Perl脚本、java对象、数据库和查询、ftp服务器或者其他的资源）。
- 用于模拟在服务器、网络或者其他对象上附加高负载以测试提供服务的受压能力，或者分析提供的服务在不同负载条件下的总性能情况。


## Jmeter环境配置和安装

#### 系统需求
由于Jmeter是Java的框架，所以需要具备 JDK 的环境，具体JDK下载地址：https://www.oracle.com/java/technologies/javase-downloads.html

JDK的安装不再赘述。

#### 验证Java的安装
```
java -version
```
截图如下：

![](https://github.com/SolerHo/Software-Testing/blob/master/Tools-Usage/Images/%E9%AA%8C%E8%AF%81Java%E5%AE%89%E8%A3%85.png)

#### 下载Jmeter
下载地址：https://jmeter.apache.org/download_jmeter.cgi

![](https://github.com/SolerHo/Software-Testing/blob/master/Tools-Usage/Images/Jmeter%E4%B8%8B%E8%BD%BD%E7%95%8C%E9%9D%A2.png)

下载相应的文件，对文件进行解压，直接切换目录到 `bin目录` 下，通过 `sh jmeter` 命令进行启动Jmeter。

![](https://github.com/SolerHo/Software-Testing/blob/master/Tools-Usage/Images/%E8%BF%9B%E5%85%A5Jmeter%E7%9A%84%E6%96%B9%E5%BC%8F.png)



