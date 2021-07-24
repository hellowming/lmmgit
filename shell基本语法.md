# shell基本操作

## 1.shell解析器

```shell
/bin/sh 
/bin/bash  #Centos默认采用此解析器
/sbin/nologin
/bin/dash
/bin/tcsh
/bin/csh
```

## 2.脚本基本操作

vim helloworld.sh

```shell 
#!/bin/bash  #指定解析器 可以理解成一个脚本的固定格式开头
echo "helloworld"
```

#### 2.1执行命令

1.sh helloworld.sh  //采用sh + 相对路径

2.sh /home/data/helloworld.sh  //sh + 绝对路径

3bash helloworld.sh

4bash helloworld .sh

另一种就是先给脚本文件赋予可执行权限 

chmod 777 helloworld.sh

./helloworld.sh 相对路径执行

/home/data/helloworld.sh  //绝对路径执行

创建一个脚本 功能是创建一个文件 再往里面添加文本内容

```shell
#!/bin/bash
touch a.txt
echo "I love you" >> a.txt
```

## 3.shell中的变量

```shell
#常用的系统变量
$HOME $PWD $HELL $USER
#显示当前的所有变量
set
BASH=/bin/bash

##自定义变量 没有类型的声明 由字母,下划线。数字组成 ，但是不能以数字开头，环境变量名建议大写
#等号两侧不能有空格
#默认都是字符串类型，所以无法直接进行数值运算
#变量的值如果有空格需要用双引号或者单引号括起来

#基本语法
变量=值 #定义变量
unset 变量 #撤销变量
readonly 变量 #声明静态变量  此变量不能unset 
a=5
unset a
b="I lone you"
readonly c=love
export b #把b提升为全局变量，可以供其他shell程序使用

###特殊变量$n $0表示脚本名称 $1~9 代表第一到第九个参数 两位数以上的参数需要用花括号 如：${11}

$# #表示输入参数个数，常用于循环
$* #所有参数，当被双引号包含的时候，所有参数是一个整体，没有双引号时和$@作用相同 “$*”是一个整体
$@ #所有参数，没双引号时 是用$1,$2,$3...的形式输出  有双引号时是“$1”,"$2","$3"..输出
$? #程序执行状态 成功或失败 成功返回0 
```

## 4.运算符

```shell
#基本语法
$((运算式)) 或 $[运算式] 或 expr 运算式 +,-,\*,/,%  (加减乘除，取余)，建议用第二种
expr 2 + 3
expr `expr 2 + 3` \* 4
a=$[(2+3)*4]

##条件判断
[条件] 条件非空即true
[hello] 为true
[] 为false
##常用的比较判断
= 字符串比较是否相同
-lt 小于[ 3 -lt 4 ] 返回true
-le 小于等于

```





