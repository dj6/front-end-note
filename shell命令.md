# shell提示符 #
- [root@funbreak ~]#
启动shell的用户名为root，当前虚拟控制台的编号funbreak，~为当前目录，即主目录的缩略表示

# linux文件系统 #
windows文件路径，例如F:\cometrue\note\front-end-note\text.txt，会告诉你究竟哪块**物理硬盘**上有文件text.txt。
linux将文件存在单个目录结构中，称为**虚拟目录**，虚拟目录包含了pc上所有存储设备的文件路径，并将其并入到一个目录结构中。
例如：/home/rich/text.txt，只是说明text.txt在文件夹下rich下，rich在home文件夹下，并没有说这个text.txt文件具体在哪块物理磁盘上。
-  /home 
主目录，linux在这里创建用户目录

# shell命令 #

## cd ##
后可跟绝对和相对路径。
- ** . **：当前目录
- **.. **：上级目录
- cd /：回到根目录

## ls ##
- -F 区分文件和目录
- -R 当前目录及其子目录
- -a 显示隐藏的文件
- -s 文件大小
- -i 显示索引值
- -sail

### 过滤输出列表 ###
- ls -sail mypro?(0个或1个)
- ls -sail mypro*（0个或无穷个）

## 创建文件 ##
- touch
eg：touch app.js

## 复制文件 ##
- cp
- 硬链接 -l 复制和源文件的文件索引相同，说明实际上是一个文件
- 软链接 -s 索引节点不同，链接文件只有源文件中的信息，没有源文件数据

##重命名文件##
- mv 文件名改变，文件索引不变，时间戳不变（软链接问题）

## 删除文件 ##
- rm 
- 硬链接会一直维持这个索引节点号直到删除最后一个硬链接他的文件
- 删除软链接指向的文件后，软链接也变成无效文件了

## 查看文件 ##
- stat 文件状态
- file 文件类型（可执行，文本，数据-不可执行也不能打印）
- cat 文件全部内容 -n加行号
- tail 文件尾部内容
- head 文件头部内容
- 搜索文件中的数据（加行号） grep abb test.txt -n

## 编辑文件 ##
- vim 

## 创建目录 ##
- mkdir

## 删除目录 ##
- rmdir
- -r 递归删除目录下的文件，直到删除目录自身

## 进程 ##
- 显示所有进程 ps -A(ps -ef)
- 实时监测进程 top
- 结束进程 
kill PID
killall http*

## 磁盘空间 ##
- df -h 还有多少磁盘空间
[root@funbreak ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/vda1        20G  3.1G   16G  17% /
tmpfs           246M     0  246M   0% /dev/shm
- free -m 内存（以M为单位）
[root@funbreak ~]# free
             total       used       free     shared    buffers     cached
Mem:        502272     494440       7832          0     143232      76532
-/+ buffers/cache:     274676     227596
Swap:            0          0          0
- du 当前目录下所有的文件、目录磁盘使用情况

## 解压、安装 ##
- wget url 下载
- tar 解压、压缩
- yum install从软件中心库下载并安装（yum install vim）
