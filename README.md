### phpstorm 激活码链接地址： https://3.jetbra.in/
### ppa 仓库搜搜地址： https://launchpad.net/
### PHP Event Dispatcher PSR-14   https://dev.to/fadymr/php-create-your-own-php-psr-14-event-dispatcher-200b
### xhprof  https://www.cnblogs.com/jkko123/p/10697575.html
### docker hub 镜像加速可用目前    https://gist.github.com/y0ngb1n/7e8f16af3242c7815e7ca2f0833d3ea6?permalink_comment_id=5082662#gistcomment-5082662

### PHP修改linux时间
```
SystemValidate::validate($param, 'time');
$dateTime = $param['datetime'];
async_job(function () use ($dateTime) {
    $serverDate = date('Y-m-d H:i:s', strtotime($dateTime));
    exec('sudo timedatectl set-ntp no');
    exec('sudo timedatectl set-timezone Asia/Shanghai');
    exec("sudo date -s \"$serverDate\"");
    exec('sudo hwclock --systohc');
});
```

### php7.4 + oci8拓展
```
1：mkdir /opt/oracle
2:上传3个文件到这个目录下 sdk-10.2.0.5.0-linux-x64.zip  basic-10.2.0.5.0-linux-x64.zip  oci8-2.2.0.tgz
3：unzip basic-10.2.0.5.0-linux-x64.zip
4：unzip sdk-10.2.0.5.0-linux-x64.zip
5: unzip oci8-2.2.0.tgz
6: ln -s /opt/oracle/instantclient_10_2/libclntsh.so.10.1 /opt/oracle/instantclient_10_2/libclntsh.so
7：ln -s /opt/oracle/instantclient_10_2/libocci.so.10.1 /opt/oracle/instantclient_10_2/libocci.so
8： sudo -s
9： echo /opt/oracle/instantclient_10_2 > /etc/ld.so.conf.d/oracle-instantclient.conf
10： ldconfig
11： cd oci8-2.2.0
12： apt install autoconf
13： phpize
14： ./configure --with-oci8=shared,instantclient,/opt/oracle/instantclient_10_2
15： make install
16： echo "extension=oci8.so" |sudo tee -a /etc/php/7.4/cli/php.ini
17： echo "extension=oci8.so" |sudo tee -a /etc/php/7.4/fpm/php.ini
18： systemctl restart php7.4-fpm

```

### ubuntu 18 安装php7.4
```
sudo apt -y install software-properties-common
sudo add-apt-repository ppa:andykimpe/php
sudo apt update && sudo apt upgrade
sudo apt install php7.4
```
