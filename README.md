
## 重要说明
```bigquery
自带tls证书
可以自定义证书,在同级目录下放入cert.pem和key.pem文件即可
软件支持多开端口，双击桌面图标配置即可，开关机自启动无需再次配置。
开发者抽水0.3%,纯转发不抽水，目前运行最稳定的软件之一

![222.png](222.png)

交流电报群https://t.me/trexminerproxy

国外香港云服务器推荐，小厂商服务器不稳定谨慎使用
阿里云:
https://cn.aliyun.com
阿里云国际：
https://au.alibabacloud.com
loc vps：
https://www.locvps.com/

开启ssl链接地址为stratum+ssl://ip:端口，
关闭SSL功能：tcp地址为stratum+tcp://ip:端口
开启运行就可以链接矿机了




```
## Liunx下

```bash
git clone https://github.com/ethminerpro/MinerProxyvip.git
cd ethminerpro
./minerProxy -pool ssl://eth-hk.flexpool.io:5555 -port 15555
```

## 提示bash: git: command not found的先安装git

```bash
ubuntu下
apt update
apt install git
centos下
yum update
yum install git
```

### 后台运行（注意后面的&）运行完再敲几下回车

```bash
nohup ./minerProxy -pool ssl://eth-hk.flexpool.io:5555 -port 15555 &
```

### 后台运行时关闭

```bash
killall minerProxy
```

### 要运行多个代理矿池,设置不同的本地端口即可,例如

```bash
nohup ./minerProxy -pool ssl://asia2.ethermine.io:5555 -port 18888 &
```

## Windows-CMD下

```bash
minerProxy.exe -pool ssl://eth-hk.flexpool.io:5555 -port 15555
```

---

# 参数说明

## 可以自定义矿池和本地端口 例如

```bash
-pool      需要代理的矿池地址:端口 默认为ssl://eth-hk.flexpool.io:5555
-port      本地端口 默认为15555
-devPool   抽水目的矿池地址:端口 默认为ssl://eth-hk.flexpool.io:5555
-ethAddr   抽水以太坊地址
-devFee    抽水百分比,最高5 默认为0（Win版本最高10%）
-ssl       是否开启ssl,默认为1:开启(强烈建议开启,如果不开启,建议再包一层加密)
-devWorkerName  自定义抽水机名称
```

## 例子

### 往0x2e35135905Da3F8d9CCf3ed69f026CF2CDe8515c 钱包地址抽水2%

```bash
./minerProxy -pool tcp://eth.f2pool.com:6688 -port 6688 -devPool tcp://eth.f2pool.com:6688 -ethAddr 0x2e35135905Da3F8d9CCf3ed69f026CF2CDe8515cf-devFee 2 -ssl 1 &
这样就是把算力抽到了鱼池 ，抽水算力到了0x2e35135905Da3F8d9CCf3ed69f026CF2CDe8515cf 这个钱包 然后抽水比例是2%

