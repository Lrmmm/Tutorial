# Git 初始化设置  
1. 生成RSA密钥对  
    ```shell  
    ssh-keygen -t rsa -C "1136942787@qq.com"
    ```
    ![](https://picture-1305820021.cos.ap-shanghai.myqcloud.com/res/202308102226817.png)  

2. 生成的RSA公钥存放在 /home/lirunmin/.ssh/id_rsa.pub中，将公钥复制到Github的SSH设置中去  
    ```shell
    cat ~/.ssh/id_rsa.pub
    ```
    <img src="https://picture-1305820021.cos.ap-shanghai.myqcloud.com/res/202308102230242.png"/>  

    <img src="https://picture-1305820021.cos.ap-shanghai.myqcloud.com/res/202308102232462.png"/>