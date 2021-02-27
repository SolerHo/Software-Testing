## Linux命令知识

参考资源：https://www.w3cschool.cn/linux/linux-command-manual.html

⚠️说明：主要以自己使用的为主，包括 centos 和 ubuntu 混合命令。如有疑问，请提issue。thx for everyone。

## 一、Linux终端中常用的快捷键

| 快捷键          | 功能                                       | 备注                                     |
| --------------- | ------------------------------------------ | ---------------------------------------- |
| Ctrl + a / Home | 跳转到命令行的开头                         | 主要是在输入内容比较多时使用             |
| Ctrl + e        | 跳转到命令行的末尾                         | 输入过多，中间修改完成时使用。           |
| Ctrl + I        | 清除屏幕内容                               | 相当于使用clear清屏                      |
| Ctrl + c        | 终止命令                                   |                                          |
| Ctrl + z        | 转入后台运行，如果当前user退出就会停止。   |                                          |
| Ctrl + d        | 退出shell命令，或者是logout。              |                                          |
| Ctrl + r        | 在历史命令中查找                           | 主要是输入关键字即可查询。               |
| history         | 显示执行过的历史命令                       | 和 Ctrl + r 同样操作                     |
| Ctrl + (x u)    | 按Ctrl的同时先后按 x 和 u ，撤销上一个操作 | 小心使用rm -rf * ,具体没试过能不能撤销。 |

## 二、Linux概述

### 1、Linux简介

Linux ： Linux is not Unix

`林纳斯·托瓦兹` 在受到Minix 和 Unix思想的启发下，1991年创立。

linux是 `自由` 和 `开源源代码` 的 类Unix OS。

  Linux是遵循GNU 通用公共许可证（GPL）的，任何人或者机构都可以自由使用Linux的所有底层源代码。

### 2、个人常用Linux版本

- Centos 7.6 或者Centos 8 【私人喜欢使用】
- Ubuntu 18.04 【公司默认开发环境】
- Kali Linux系统 【之前研究过网络安全和学习渗透测试时经常使用】
- Tlinux 系统 ——腾讯基于Centos系统进行二次开发系统 【公司使用最多】

### 3、Linux系统安装

目前针对系统的安装教程很多，具体不细化

- Centos ：https://www.w3cschool.cn/linux/linux-install.html
- Ubuntu ：https://www.cnblogs.com/zliW/p/13303736.html

### 4、常使用的终端远程连接工具

以下工具主要是个人使用，为了使用Windows时可以直接连接开发机。

- Termius ： https://www.termius.com/
  - 支持Windows、Mac OS、Linux、IOS、Android系统
- MobaXterm ：https://mobaxterm.mobatek.net/download.html
  - 只支持Window

工具很多，适合自己才是最好的工具。

### 5、本地传文件到Linux中的工具

Windows中使用 **WinSCP**。

mac中使用：【[Filezilla](https://www.filezilla.cn/download)】在linux和Windows platform中均支持。

### 6、Ubuntu中推荐小工具

- tmux ————> 【具体使用方法：[ubuntu中的tmux使用小教程]()】

## 三、系统相关的两个小问题

### 1、系统启动过程

内容参考：https://www.w3cschool.cn/linux/linux-system-boot.html

内容很详细尽，个人没必要在重复一遍。

### 2、Linux系统的一般目录结构

如图所示：

![Linux目录结构](Images/Linux%E7%9B%AE%E5%BD%95%E7%BB%93%E6%9E%84.png)

各个目录说明：

| 目录   | 全称                            | 功能                                                         |
| ------ | ------------------------------- | ------------------------------------------------------------ |
| /bin   | Binaries(二进制文件)            | 存放经常使用的命令                                           |
| /boot  | 无                              | 存放Linux启动时所需的核心文件。包括：链接文件以及镜像文件。  |
| /data  | 无                              | 自建目录                                                     |
| /dev   | Device(设备)                    | 存放Linux的外部设备。                                        |
| /etc   | Etcetera(等等)                  | 存放系统管理所需的配置文件和子目录。⚠️如果修改文件，会导致系统无法启动。 |
| /home  | 无                              | 主目录，在Linux中，每个用户都有各自目录，一般以用户的账号命名。 |
| /lib   | Library(库)                     | 存放系统中最基本的动态连接共享库。                           |
| /media | 无                              | 系统自动识别的设备，例如U盘和光驱，识别后即可挂载到该目录下。 |
| /mnt   | 无                              | 系统提供该目录的是为了让用户临时挂载别的文件系统。           |
| /opt   | optional                        | 给主机额外安装软件所摆放的目录。                             |
| /proc  | processes(进程)                 | /proc时伪文件系统（也即虚拟文件系统），存储当前内核运行状态的一些特殊文件 |
| /root  | 无                              | 系统管理员，超级权限的用户主目录。                           |
| /sbin  | superuser Binaries              | 超级用户二进制文件，主要存放系统管理员root使用的系统程序。   |
| /run   | 无                              | 临时文件系统，存储系统启动以来的信息。系统重启时，会被删除或者覆盖。 |
| /srv   | 无                              | 存放一些服务启动后需要提取的数据。                           |
| /sys   | 无                              |                                                              |
| /tmp   | temporary(临时)                 | 存放一些临时文件                                             |
| /usr   | unix shared resources(共享资源) | 用户应用程序和文件目录，类似Windows中programs files。        |
| /var   | variable(变量)                  | 存放扩充文件                                                 |

## 四、命令基本格式

### 1、命令提示符

```shell
[root@centos8 ~]# 
```

- `[]`：这是提示符的分隔符号，没有特殊含义。
- `root`：显示的是目前使用的当前登录用户root。
- `@`：分隔符号，没有特殊含义。
- `centos8`：当前系统的简写主机名（一般默认主机名是 localhost）。
- `~`：代表用户当前所在的目录，此时用户当前所在的目录是root目录。
- `#`：命令提示符。**超级用户是#，普通用户是$**。

### 2、命令的基本格式

```shell
[root@centos8 ~]# command [option] [param]
```

- `[option]`: 调整命令的功能
- `[param]`：命令操作的对象

### 3、一些概念

相对路径：不以`"/"`为始，例如：linux/cxx

绝对路径：路径中一定含`"/"` 作为开始，例如：/data/linux。

```shell
./ : 代表当层目录
.. : 从当前目录后退一个目录层
- ：上一次所在目录
```

### 4、查看命令用法

语法格式：

```shell
command --help
#示例
cd --help
```

例如截图如下：

![cd-help](Images/cd-help.png)

## 五、文件和目录操作命令

### 1、cd命令

`cd` : 切换工作目录，语法格式：

```shell
cd [option] [param]
#示例
cd /data/linux/cxx
```

说明：

- 名称：change directory
- 执行权限：所有用户
- 所在路径：shell内置命令
- `[option]`：常见的有两种情况：
  - `-L`：（默认）如果切换目标目录为符号链接，则直接切换。
  - `-P`：如果切换的目标目录为符号链接，则切换到它指向的物理位置目录。
- `[param]`：相对路径（以当前目录为参照）或者是绝对路径（以根目录作为参照）。

常见用法：

```shell
cd ~ # 当前用户的home目录
cd - # 上一次所在目录
cd /data/linux/cxx # 切换到/data/linux/cxx目录，此时WS（workspace）在cxx目录下
cd ./ # 当前目录，符号(/)加不加无影响，个人习惯
cd .. # 上一级目录
```

### 2、ls命令

`ls`：显示目录下的内容。语法格式如下：

```sh
ls [option] [dir]
#示例
ls -l /data/linux # 显示linux目录下的内容
```

说明：

- 名称：list
- 所在路径：`/bin/ls`
- 执行权限：所有用户
- 常见的[option]有：
  - `-a`：显示所有的文件（包括隐藏文件）。
  - `-l`：长格式显示（不包括隐藏文件）
  - `-h`：显示文件文件大小。常用方式：`ll -h`。
  - `-i`：显示文件节点号。

**`ls -l` 中信息说明**：

```shell
[root@centos8 data]# ls -l
total 2513740
-rw-r--r-- 1 root root 2571206658 Nov 14  2019 cuda-repo-rhel8-10-2-local-10.2.89-440.33.01-1.0-1.x86_64.rpm
drwxr-xr-x 2 root root          6 Jan 23 22:33 cxx
-rw-r--r-- 1 root root        672 Dec  2 23:06 dockerfile
drwxr-xr-x 2 root root          6 Sep 27 10:38 python
-rw-r--r-- 1 root root        315 Dec  2 22:50 requirements.txt
drwxr-xr-x 2 root root         95 Sep 25 15:45 soler
-rw-r--r-- 1 root root    2848270 Dec  3 01:08 wget-log
# 权限    引用计数 所有者 所属组 大小   文件修改时间  文件名
```

### 3、pwd命令

`pwd`：查询所在目录信息。语法格式：

```sh
pwd [-L|-P] 
#默认是-L，和cd 命令中 [option]中的用法类似
```

说明：

- 名称：print working directory
- 所在路径：`/bin/pwd`
- 执行权限：所有用户

### 4、mkdir命令

`mkdir`：创建空文件夹。语法格式：

```sh
mkdir [option] dir_name
#示例
mkdir cxx # 创建cxx目录
```

说明：

- 名称：make directory
- 所在路径：`/bin/mkdir`
- 执行权限：所有用户
- [option]有：
  - `-p`：递归建立目录
  - `-m`：建立目录时，设置该目录的权限。

### 5、touch命令

`touch`：创建空文件或者修改文件时间戳。语法格式：

```sh
touch [option] file_name
#示例
touch helloworld.c
```

说明：

- 名称：create file or change file timestamps
- 所在路径：`/bin/touch`
- 执行权限：所有用户
- [option]的内容有：
  - `-r`：把指定文件或目录的日期时间改为参考文件或者目录的时间。

### 6、cat命令

`cat`：查看文件内容。语法格式：

```sh
cat [option] file_name
#示例：查找文件中 Hello 并显示内容
# cat -n helloworld.cpp | grep Hello # grep 用法后续会提及
5   cout << "Hello, world!" << endl; # 文件中查找到的内容所在位置
```

