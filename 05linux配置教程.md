# 防火墙相关  
```shell
sudo systemctl status firewalld     #检查防火墙状态
sudo firewall-cmd --zone=public --add-port=16555/tcp --permanent    #放通tcp的16555端口
sudo firewall-cmd --reload  #重新加载firwall
sudo firewall-cmd --list-ports #
sudo netstat -tulpn | grep 16555

```