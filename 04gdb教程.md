```shell
(gdb) show scheduler-locking
(gdb) set scheduler-locking on
```
## 安装最新版GDB
```shell
https://ftp.gnu.org/gnu/gdb/
./configure --prefix=/usr/
make
make install
```

## 查看虚函数表
```shell
(gdb) p (long long*)*((long long*)0x402040)
```
