一：SHELL

"" 界定范围
'' 界定范围，屏蔽特殊符号。
``获取执行结果    $( ) 效果一样  例如： a=`ls`  a=$(ls)

案例：创建ftp 账号的脚本：
#!/bin/bash
useradd $1
useradd -d /data01/ftpfile/$1 -s /sbin/nologin $1

echo $2 | passwd -- stdin $1
