# install

```
sudo stap-prep

#安装内核 devel
sudo yum localinstall kernel-devel-3.10.0-1127.el7.x86_64.rpm
sudo yum localinstall kernel-debug-devel-3.10.0-1127.el7.x86_64.rpm


#查询进程 lua 相关探针
sudo stap -l 'process("xxx/lua_process").function("lua_*")'


#tips

ERROR: module version mismatch (#1 SMP Tue Sep 25 1452 CDT 2018 vs #1 SMP Wed Sep 26 1511 UTC 2018), release 3.10.0-862.14.4.el7.x86_64

vim /usr/src/kernels/3.10.0-862.14.4.el7.x86_64/include/generated/compile.h

#define UTS_VERSION "#1 SMP Tue Sep 25 1452 CDT 2018"
改为
#define UTS_VERSION "#1 SMP Wed Sep 26 1511 UTC 2018"
```

# usage

```
lua_bt -h
stackcollapse-stap.pl a.bt > a.cbt
flamegraph.ph a.cbt > a.svg
```
