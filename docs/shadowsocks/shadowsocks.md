# shadowsocks

## 下载

> 打开服务端rust版本的发行页。
>
> https://github.com/shadowsocks/shadowsocks-rust/releases
>
> 在最新发行版的“Assets”中找到对应自己操作系统的二进制文件包。
>
> 我的系统是Ubuntu，CPU是x86架构，下载的文件包是“shadowsocks-v1.12.4.x86_64-unknown-linux-gnu.tar.xz”。
>
> 执行以下命令，下载文件包：

```shell
wget https://github.com/shadowsocks/shadowsocks-rust/releases/download/v1.12.4/shadowsocks-v1.12.4.x86_64-unknown-linux-gnu.tar.xz

```

## 安装

文件下载完成后，先解压：

```shell
xz -d shadowsocks-v1.12.4.x86_64-unknown-linux-gnu.tar.xz

tar -xvf shadowsocks-v1.12.4.x86_64-unknown-linux-gnu.tar
```

## 配置

在“ssserver”所在的路径下，使用touch命令创建一个配置文件：

```shell
touch config.json
```

使用vim编辑这个配置文件，并写入下面示例中的配置：

```shell
{
    "server": "10.20.30.40",
    "server_port": 1111,
    "password": "123456abcdef",
    "method": "aes-256-gcm",
    "local_address": "127.0.0.1",
    "local_port": 1080
}
```

## 启动

使用以下命令，让ssserver引用配置文件并后台运行：

```shell
./ssserver -d -c config.json
```

