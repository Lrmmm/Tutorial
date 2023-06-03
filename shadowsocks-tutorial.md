# Shadowsocks-lib 搭建教程
ref : https://github.com/zhaoweih/Shadowsocks-Tutorial   
ref : https://github.com/Alvin9999/new-pac/issues/1407  
ref : https://tool.chinaz.com/port  
ref : https://cloud.tencent.com/developer/article/1869020  
ref : https://medium.com/@thomas_summon/%E6%B5%85%E8%B0%88vpn-vps-proxy%E4%BB%A5%E5%8F%8Ashadowsocks%E4%B9%8B%E9%97%B4%E7%9A%84%E8%81%94%E7%B3%BB%E5%92%8C%E5%8C%BA%E5%88%AB-b0198f92db1b

1. 运行安装脚本  
    ```shell
    wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh

    chmod +x shadowsocks-all.sh

    ./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
    ```  
2. 选择ss的服务端版本  
    <img src="https://picture-1305820021.cos.ap-shanghai.myqcloud.com/res/202306040006895.png"/>  
3. 填写ss的登陆密码
    <img src="https://picture-1305820021.cos.ap-shanghai.myqcloud.com/res/202306040008258.png"/>  
4. 输入ss要监听的服务端端口号
    <img src="https://picture-1305820021.cos.ap-shanghai.myqcloud.com/res/202306040008735.png"/>  
5. 选择加密方式，一般选择13
    <img src="https://picture-1305820021.cos.ap-shanghai.myqcloud.com/res/202306040009561.png"/>  
6. 一路回车即可  
7. 关闭防火墙服务  
    ```shell
    systemctl stop firewalld
    systemctl disable firewalld
    ```  
8. 优化服务器连接安装BBR加速服务
    ```shell
    wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh && chmod +x bbr.sh && ./bbr.sh
    ```  
9. 用wrap伪装VPS的ip，原理就是把VPS的出口流量转发到另一个IP（由cloudfare免费提供）上进行代理  
    ```shell
    bash <(curl -fsSL git.io/warp.sh) d
    ```  
10. 工具使用说明  
    ```shell
    /etc/init.d/shadowsocks-libev start
    /etc/init.d/shadowsocks-libev stop
    /etc/init.d/shadowsocks-libev restart
    /etc/init.d/shadowsocks-libev status
    ./shadowsocks-all.sh uninstall  # 卸载
    ```  
    启用shadowsocks多端口：https://stanleyzhao.xyz/2019/06/01/%E5%A6%82%E4%BD%95%E5%90%AF%E7%94%A8Shadowsocks%E7%9A%84%E5%A4%9A%E7%AB%AF%E5%8F%A3/