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
- n 判断是否非空   [ - n "$a" ]   变量需用引号引起来。否则若为空，会报错
- z 判断是否为空

1、逻辑测试  ：  
&&  前面任务成功后，才执行之后的任务
||  前面的任务失败后， 才执行之后的任务
例如:  [ - z $1 ]  && exit
yum -y install $1 & >/dev/null
 systemctl restart $1
 systemctl enable $1
 
 #!/bin/bash
 read -p "请输入用户名" n
 [ -z $n ] $ && echo "请输入名字" && exit
 user -add $n
 
 2、数字的测试：
 -eq 等于  -ne不等于 -gt大于  -ge大于等于  -lt小于  -le小于等于
 
 超过3人登录，发邮件
 #!/bin/bash
 x= `who | wc -l`
 [ $x -gt 3] && echo "有人登录服务器" | mail -s test root
 
 3、文件的测试
 -e 是否存在  -f  是否存在且为普通文件  -d 是否存在且为目录
 
 
 ===============================================================================================
 if 判断
 单分支
 if  条件测试 ; then
     执行指令
 fi
 
 双分支
 if  条件测试; then
    执行指令1
 else
    执行指令2
 fi
 
 多分支
  if  条件测试; then
    执行指令1
 elif  添加测试2 ; then
    执行指令2
 else
    执行指令3
 fi
 
 
 
