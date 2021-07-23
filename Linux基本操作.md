# Linux入门

## 1.目录结构

/ 根目录

/下有root , bin , boot , dev , etc , home , var , lib , usr , media ......

/bin 是Binary 的缩写，这个目录存放的是经常使用的命令

/sbin 这里放的是系统管理员使用的系统管理程序

/home 存放普通用户的主目录，一般目录名是以用户账户命名

/root 超级权限者用户的主目录

/lib jar 包之类的

/etc 配置文件和子目录

/usr 用户的应用程序和文件

/opt 额外安装软件所摆放的目录

/var 把经常修改的目录放在这里，包括各种日志文件

## 2.vi/vim编辑器

```shell
#注释
#如果hello.sh存在的情况下会进入一般模式
#再按i进入编辑模式
#i当前光标行前，a当前光标后，o当前光标行的下一行，I光标所在行最前，A光标所在行最后，O当前光标上一行
#编辑完成后 按esc退出编辑模式，然后按：w保存，：q退出 ，  ：！强制执行 ,  :wq!强制保存退出
#快捷键保存退出 shift + zz
vim hello.sh
```

## 3.常用命令

```shell
cd 
cd .. #返回上一级
tab #补齐
ctrl + c #停止进程
ctrl + l #请屏
ctrl + q #退出
上下键 #查找执行过的命令
pwd #查看当前位置的绝对路径
ll #列车文件
ls -a #列出全部文件，连同隐藏文件
ls -l #把文件的属性也列出来

#创建/删除文件和目录
mkdir lmm #创建目录
mkdir -p lmm/lmm01/lmm02 #创建多级目录
rmdir lmm #删除目录
touch lmm.sh #创建文件
cp lmm tolmm #复制文件，从前复制到后
cp -r 目录1 目录2 #递归复制目录1到目录2
rm lmm.txt #删除文件
rm -r 目录 #递归删除目录中的内容
#执行删除命令的时候一定要谨慎，不要轻易执行 rm -rf  -f 是强制删除
#删除个人的临时文件就习惯性用rm 文件 不要带其他参数保证安全

#查看文件 
cat a.txt

#移动文件或重命名
mv oldname newname #重命名文件
mv /temp/movefile /targt/Folder #移动文件

#查看日志
head wenjian #默认查看文件头10行内容
head -n 20 wenjian #查看头20行文件内容
tail wenjian #重文末展示
tail -n 20 wenjian #展示文件末尾20行数据
more #流式读取文件，可以避免cat 文件时由于文件过大而OOM

date #日期函数
dt=`date -d "1 day ago" +%Y%m%d`
date #2021年 08月 06日 星期五 20:23:23 CST
date +%Y #2021 显示当前年份
date +%m #08 显示当前月份
date +%d #06 显示当前是哪天
date +%Y%m%d #20210806
date +"%Y-%m-%d %H:%M:%s" #2021-08-06 20:23:23
date -d '1 days ago' #显示昨天时间
date -d '-1 days ago' #显示明天时间
date -s "2021-08-06 20:23:23" #设置系统当前时间

su lmm #切换用户，只能获取执行权限，不能获取环境变量
su - lmm #切换用户，获取执行权限的同时还能获取环境变量
sudo #设置普通用户具有root权限
chmod 777 #修改文件的权限 可读可写可执行
ls | grep -n test #查看某文件在第几行

sz #下载文件
rz #上传文件

#高级命令
top 内存
netstat 
ps
aux 
io 网络io
df -h 磁盘
```







