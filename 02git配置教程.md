# Git 初始化设置 && SSH 初始化设置
## Git初始化设置
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

3. 设置git的Email和name
    ```shell
    git config --global user.email "you@example.com"  
    git config --global user.name "Your Name"
    ```

## SSH初始化设置免密登录  
1. 本地生成ssh密钥对：id_rsa和id_rsa.pub  
    ```shell
    ssh-keygen
    ```
2. 将生成的SSh私钥id_rsa路径写入VScode的SSH配置文件中  
    <img src="https://picture-1305820021.cos.ap-shanghai.myqcloud.com/res/202308102254288.png"/>  

3. 将本地的SSH公钥添加到服务端的authorized_keys中  
    ```shell
    vim ~/.ssh/authorized_keys
    ```
4. 部分服务器要更改目录权限
   ```shell
   chmod 700 .ssh
   chmod 600 .ssh/authorized_keys
   ```
