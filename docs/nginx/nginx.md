# nginx

## 下载

> **第一步：下载nginx压缩包**
>在这里可以去nginx官网下载->[点我下载nginx](http://nginx.org/en/download.html)
> 也可以直接使用wget命令下载，指令如下所示（请根据自己的需求进行下载）：

```shell
wget -c https://nginx.org/download/nginx-1.19.10.tar.gz
```

## 安装

安装 nginx 需要先将官网下载的源码进行编译，编译依赖 gcc 环境。安装指令如下：

```shell
apt-get install gcc
```

**2. 安装PCRE pcre-devel**

Nginx的Rewrite模块和HTTP核心模块会使用到PCRE正则表达式语法。这里需要安装两个安装包pcre和pcre-devel。第一个安装包提供编译版本的库，而第二个提供开发阶段的头文件和编译项目的源代码。安装指令如下：

```shell
yum install gcc-c++
```

**3.安装zlib**

zlib库提供了开发人员的压缩算法，在Nginx的各种模块中需要使用gzip压缩。安装指令如下:

```shell
apt-get install libpcre3 libpcre3-dev
apt-get install zlib1g zlib1g-dev
```

**4.安装Open SSL**

nginx不仅支持 http协议，还支持 https（即在 ssl 协议上传输 http），如果使用了 https，需要安装 OpenSSL 库。安装指令如下：

```shell
sudo apt-get install openssl 
sudo apt-get install libssl-dev
```

## 配置

在“ssserver”所在的路径下，使用touch命令创建一个配置文件：

```shell
tar -zxvf nginx-1.10.1.tar.gz
```

**额外说明**：如果需要开始https支持，这里请不要直接执行`./configure`，即不要直接执行该脚本，而是在该脚本后面加上SSL模块，请执行如下命令替代 `./confingure` :

```shell
./configure --with-http_ssl_module
```

第四步：编译安装nginx
这里和redis的编译安装比较类似，首先在当前目录（/usr/local/nginx-1.10.1）进行编译。输入make即可

```shell
make
```

然后回车，如果编译出错，请检查是否前面的4个安装都没有问题。
编译成功之后，就可以安装了，输入以下指令：

```shell
make install
```

