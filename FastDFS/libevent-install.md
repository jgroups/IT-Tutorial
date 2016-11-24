1.先用：ls -al /usr/lib | grep libevent  查看是否已安装，如果已安装且版本低于1.3，则先通过：rpm -e libevent —nodeps 进行卸载。
 
2.下载libevent安装包：libevent-1.4.12-stable.tar.gz，然后解压。
 
3.切换到解压后的 libevent 主目录：cd libevent-1.4.12-stable
 
4.依次执行：
 
<code>
./configure –prefix=/usr （或 ./configure --program-prefix=/usr） 
make  
make install
</code>
 
注意： 
1）执行 make install 时可能需要 root 权限。
2）libevent会安装到 /usr/lib 或 /usr/local/lib 下。
 
5.测试libevent是否安装成功：ls -al /usr/lib | grep libevent（或 ls -al /usr/local/lib | grep libevent） 
出现文件以及版本信息表示安装成功.
 
6.如果libevent的安装目录为/usr/local/lib下，则还需要建立 libevent-1.4.so.2 到 /usr/lib 的软连接，这样其他程序运行时才能找到libevent库：
<code>ln -s /usr/local/lib/libevent-1.4.so.2  /usr/lib/libevent-1.4.so.2</code>
