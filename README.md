                                                              一：SHELL
$1 脚本后的第一个参数
$? 上一个命令是否执行成功
$$  当前程序的进程号
"" 界定范围
'' 界定范围，屏蔽特殊符号。
``获取执行结果    $( ) 效果一样  例如： a=`ls`  a=$(ls)

案例：创建ftp 账号的脚本：
#!/bin/bash
useradd $1
useradd -d /data01/ftpfile/$1 -s /sbin/nologin $1
echo $2 | passwd -- stdin $1

===========================
条件测试:  ==  判断两边的内容是否相等  ；例如  [ root == $user ] 我是不是管理员  echo $?
- n 判断是否不为空   [ -n "$a" ]  
