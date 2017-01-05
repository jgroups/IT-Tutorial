#1、安装Xshell_5.0.0.37_setup
#2、安装VMware_workstation_full_12.5.0.11529（安装的时候不要选择centOS镜像文件选择空那项）
#3、将redis传到虚拟机系统中
（1、 设置网络重启虚拟机
     安装gcc和c++ :      yum install -y gcc g++ gcc-c++
     安装vim    :     yum -y install vim*    

#2、解压、编译、安装redis-3.2.5：
tar -zxvf redis-3.2.5.tar.gz -C /usr/src/
cd /usr/src/redis-3.2.5/
make && make install

#3、创建redis相关目录：
mkdir -p /home/redis/bin
mkdir -p /home/redis/log
mkdir -p /home/redis/pid
mkdir -p /home/redis/db

#4、将可执行文件复制到自己的安装目录：/home/redis/
          ln -s /usr/local/bin/redis-*   /home/redis/bin/

#5、复制配置文件到自己的安装目录：/home/redis/
          cp redis.conf /home/redis/
          cp sentinel.conf /home/redis/

#6、进入自己的安装目录，编辑sentinel.conf配置文件：
cd /home/redis/
vim /home/redis/sentinel.conf）
#4、关闭虚拟机防火墙
     service iptables stop
