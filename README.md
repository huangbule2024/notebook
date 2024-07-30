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
