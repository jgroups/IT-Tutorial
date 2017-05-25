## 安装Xshell_5.0.0.37_setup
## 安装VMware_workstation_full_12.5.0.11529（安装的时候不要选择centOS镜像文件选择空那项）
## 安装准备
- 设置网络,重启虚拟机
- 安装gcc和c++: `yum install -y gcc g++ gcc-c++`
- 安装vim:'yum -y install vim*`

## Redis安装
### 解压、编译、安装redis-3.2.5
 - 解压
`tar -zxvf redis-3.2.5.tar.gz -C /usr/src/`
 - 进入目录
`cd /usr/src/redis-3.2.5/`
 - 编译安装
`make && make install`

### 创建redis相关目录
 - 创建目录:`mkdir -p /home/redis/bin`
 - 创建目录:`mkdir -p /home/redis/log`
 - 创建目录:`mkdir -p /home/redis/pid`
 - 创建目录:`mkdir -p /home/redis/db`
 
### 将可执行文件复制到自己的安装目录：/home/redis/
 `ln -s /usr/local/bin/redis-*  /home/redis/bin/`
 
### 复制配置文件到自己的安装目录：/home/redis/
`cp redis.conf /home/redis/`
`cp sentinel.conf /home/redis/`

### 进入自己的安装目录，编辑sentinel.conf配置文件：
 - 进入目录:
`cd /home/redis/`
 - 编辑文件:
`vim /home/redis/sentinel.conf`

### 关闭虚拟机防火墙
`service iptables stop`
