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

4.1.2 【Should】存量可延期使用版本
Windows Server、 2016及以上、仅限存量扩容与维护，不允许新项目选用。

Linux Server、EulerOS 2.9、openEuler 20.03
以下软件包或平台可保留在
Redhat平台运行：Oracle DB、
Hyperion、Biee、Datastage、
Bo、Oracle EBS、Winchill、
Tibco、HTM、OAM、SOA、
Weblogic、Siebel等

4.1.3 【Must】待日落版本
Windows Server
2012 R2
2008
2003
已EOS，禁止新增

Linux Server
EulerOS 2.8及以下
Redhat 7及以下
CentOS 7及以下
Ubuntu 20及以下
SLES 11及以下
已EOS，禁止新增


4.2 【Should】操作系统群集使用要求
Windows Server
Windows Server Failover
Clustering 2016/2019/2022
仅限存量扩容与维护，不允许
新项目选用，如需使用须获得
系统与运营TMG批准。

Linux
Veritas Cluster Server HA 6.x
仅限存量扩容与维护，不允许
新项目选用，如需使用须获得
系统与运营TMG批准。


名称 定义
SE Standard Edition 标准版
EE Enterprise Edition 企业版
SLES SuSE Linux Enterprise Server
RHEL Red Hat Enterprise Linux （红帽企业Linux）
CentOS
Community Enterprise Operating System (社
区企业操作系统)
OEL
Oracle Enterprise Linux （甲骨文企业
Linux）

8 文件拟制/修订记录

 
 
