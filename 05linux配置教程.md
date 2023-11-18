# 防火墙相关  
```shell
sudo systemctl status firewalld     #检查防火墙状态
sudo firewall-cmd --zone=public --add-port=16555/tcp --permanent    #放通tcp的16555端口
sudo firewall-cmd --reload  #重新加载firwall
sudo firewall-cmd --list-ports #
sudo netstat -tulpn | grep 16555

```

# 安装GCC/更新最新版GCC
### 1.卸载默认GCC
```shell
rpm -q gcc  // 查看gcc版本号
rpm -e [第二步查到的版本号] 
```
### 2.安装scl和gc
```shell
yum install centos-release-scl
yum install -y devtoolset-11-gcc devtoolset-11-gcc-c++
scl enable devtoolset-11 bash
```
### 3.配置用户变量和系统变量
```shell
vim /etc/profile
PATH=$PATH::/opt/rh/devtoolset-11/root/usr/bin
export PATH
```

