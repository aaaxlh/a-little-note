# Linux系统常用单词翻译

1.new folder 新建文件夹

2.paste 粘贴

3.select all  全选

4.open in terminal  打开终端/命令行

5. keep aligned   保持对齐
6. organize desktop by name按名称组织桌面
7. change background更改背景

8.cancel 取消

9.create创造 创建

10. wallpapers 壁纸 

11.notificcations通知

12.search搜索

13.region区域

14.univetsal access通用存取

15.online accounts联机帐户

16.privacy隐私

17.sharing共享

18.sound 声音

19.power权力 权限

20.network网络

21.lock screen锁频

22.open in new tab在新标签页中打开

23.open in new window 在新窗口中打开

24.cut 剪切

25.copy 复制

26.move to移动到

27.copy to复制到

28.move to trash移到垃圾箱 删除

29.resize icon调整图标大小

30.rename重命名

31.compress压紧 压缩

32.properties 属性

# 学习笔记

命令：命令本体command+选项，控制命令的行为细节［-options］+参数，控制命令的指向目标［parameter)］

## 1.ls(list show)命令 显示指定目录下的文件及文件夹

语法： ls [-l -a -h] [路径]

-l(竖向排列展示内容)

-a（列出所有文件夹和文件，包括隐藏的）

-h （human-readable,将文件的大小的默认单位Byte调整为更合适的单位，必须和-l一起使用) 

## 2.cd(change directory)命令 切换工作目录

语法：cd+［linux路径］



## 3.pwd(print work directory) 查看当前工作目录

语法：pwd

## 4.目录表示方式

（1）绝对路径：以根目录为起点，路径描述以/开头

写法：cd /home/ittangmao/Desktop

  （2）相对路径:以当前目录为起点  路径描述无其他符号开头

写法：cd Deaktop

当用相对路径形式时，系统先在当前工作目录下查询该路径，若为查询到，则进入**已配置环境变量**的路径进行查询。**而以./开头，系统只会在当前工作目录下进行路径查询。**

(3) ./   当前目录  ~/  当前用户目录，相当与/home/user  （user为当前用户名）
	../ 上一级目录   ../../上两级目录，以此类推



## 5.mkdir命令，创建新目录（文件夹）

语法：mkdir [-p] 路径
-p 创建多级目录时，若父级目录不存在则必须添加此参数

## 6.touch命令创建文件

语法：touch 路径

## 7.cat查看文件内容

语法：cat 文件1 文件2 ... 将一个或多个文件内容输出
	   cat > newfile 创建新文件newfile，等待用户输入内容，按Ctrl+D(EOF)结束输入
	   cat >> newfile 将用户输入内容追加到文件末尾，Ctrl+D(EOF)结束输入			

## 8.more 查看文件内容 可以翻页查看

语法：more 文件
空格键：显示下一屏内容。
Enter：显示下一行内容。
d：显示半屏内容。
q：退出 more，返回命令行。
b：回退一屏内容（如果支持）。
/pattern：搜索包含 pattern 的行。按 n 跳到下一个匹配项，按 N 跳到上一个匹配项。
h：显示帮助信息。

## 9.cp 复制文件或者文件夹

语法:（1）.复制文件 cp 参数1（复制的文件内容） 参数2（复制去的地方）

（2）.复制文件夹 cp -r 参数1 参数2

## 10.mv 移动文件或者文件夹

语法：mv (-r) 参数1 参数2

**命令 mv test01.txt test01和 mv test01.txt test01/  的区别：若test01是文件夹，则两者均是将test01.txt移入该目录下；若test01是文件，则前者将该文件重命名为test01，后者报错。**

## 11.rm删除文件 文件夹

语法:rm [-r -f] 参数1 参数2 …参数N

-r 用于删除文件夹 

-f 用于强制删除（即某些文件删除需确认的，不会再弹出确认信息）

## 12.which 在环境变量中查找可执行文件

语法： which [-a] 文件名

按照 `PATH`环境变量中列出的目录顺序，逐个目录搜索指定的文件。如果找到匹配的文件，which 会输出该文件的完整路径。-a表示输出所有匹配路径，否则只输出第一个匹配路径。

所有的Linux命令的本体是一个个的二进制可执行文件，which 常用来查找查找这些命令的对应文件路径；

## 13.find 查找文件和文件夹

语法： find 起始查找路径 -name "查找文件或文件夹路径"   
（双引号不可省略；参数改为-iname时，表示忽略名称的字母大小写；查找文件可用通配符*表示）

​	   find 起始查找路径 -size +或-文件大小[单位]    （+、-表示大于、小于）

​	   find 起始查找路径 -type 特定字母  （`f`：普通文件`d`：文件夹`l`：符号链接`c`：字符设备`b`：块设备）

​	   -mtime（按修改时间查找，天为单位）-mmin（以分钟为单位）
​	   -atime（按访问时间查找，天为单位）-amin（以分钟为单位）
​	   -ctime （按状态改变时间）	-cmin

​	   可以在以上指令后添加指定命令，以达到对所查找的文件或文件夹执行命令操作的效果。如命令find . -type d -empty -delete 为删除当前路径下文件夹及子文件夹中所有空文件夹。

## 14.grep 在文中查找包含关键字的行

语法：	grep [-n] "关键字" 文件路径(内容输入端口、可以是多个)	
-n	表示在结果中显示匹配的行号
-r	会在目录及其子目录中所有文件进行查找
-i	忽略大小写
-v	显示不包含关键字的行

## 15.wc 统计文件行数、字符数等

语法：	wc [-c -m -l -w] 文件路径(内容输入端口)
不带可选参数时，依次输出行数、单词数、字节数、文件名
-c	统计文件大小字节数
-m	统计字符数量
-l	统计行数
-w	统计单词数量（以空格为两单词之间的分隔）

## 16.echo 输出指定内容

语法：	echo 内容
		  内容为 \`命令\` 时，将执行命令所得到的结果作为输出内容
		  内容为$变量名时，将变量的值作为输出内容

## 17.重定向符>、>>

语法：	输出内容的指令 >或>> 文件
		将文件内容更新或追加指令输出内容

## 18.tail 查看文件尾部内容

语法：	tail [-f -数字 -数字f] Linux	
		数字为查看尾部的行数，默认为10行；-f表示持续跟踪文件内容，文件内容更新时，输出也会更新。

## 19.常用快捷键

crtl+d 退出当前程序或用户账号，近似于命令exit
crtl+l 清屏，近似于命令clear
crtl+c 退出当前运行程序
crtl+z 将当前运行程序挂入后台
crtl+a/e 光标移动至开头/结尾	crtl+左右方向键 左右移动一个单词	
`jobs` 查看后台运行的任务；`fg %任务号`  将对应任务挂载在命令窗口
`history`显示此命令窗口输入过的指令
`!指定字符`由近到远地在输入过的指令中匹配以指定字符开头的指令并执行
crtl+r 进入字符匹配(ESC退出)，此时输入字符，会显示history第一个匹配（无前缀匹配时，会类似于关键字搜索的效果）的指令

## 20. yum/apt 安装包(rpm/deb)管理命令

语法：	yum [-y] [install | remove | search] 安装包
-y表示自动确认，无需手动确认安装或卸载过程
install：安装	remove：卸载	search：搜索

## 21.systemctl 管理服务

语法：	systemctl start | stop | status | enable | disable|restart 服务名
启动|停止|查看状态|开机自启|关闭开机自启|重启
关闭系统(poweroff)	重启系统(reboot)	挂起系统、休眠系统等
列出已加载/安装/启动等的服务

## 22. ln 构建软链接(类似于快捷方式)

语法：	ln -s 被链接目录 要链接到的目录	-s表示软链接

## 23.时间和时区

语法：	date [-d "表示时间运算的字符串"] [+格式化字符串]	
将日期依指定格式输出；-d表示对当前时间(一般是日期)进行算术计算，后面接如"+1 day"(日期加一天)、"-1 month"(日期减一个月)等字符串，支持year、month、day、hour、minute、second
格式化字符串为：	%Y：年	 %y：年份后两位数	%m：月	%d：日	%H：小时	%M：分钟	%S：秒	%s：从1970-01-01 00:00:00 UTC到现在的秒数	

修改时区，将/etc/localtime 软链接到对应时区配置文件
ntp软件自动同步时间： ntpdate -u 时间更新服务器网址

## 24.IP地址和主机名

IP地址: a.b.c.d	a、b、c、d为0~255的数字
127.0.0.1用于指代本机
0.0.0.0	可以用于指代本机；可以在端口绑定中确定绑定关系；服务器配置中表示接受任意网络接口的连接请求；可以作为默认路由器目标；可以表示未分配的IP地址

主机名用于标识一个计算机；
通过域名（主机名）解析，计算机先在本地相关文件（hosts）查询是否有对应IP地址，若未找到再通过联网去公开DNS服务器查找。从而实现通过域名访问对应IP

配置Linux固定IP  修改对应配置文件，DHCP表示自动获取IP地址

## 25.网络请求和下载

`ping`命令检查网络服务器是否可联通
ping [-c 次数] ip或域名	-c表示检查次数，不使用该选项则持续检查

wget 非交互式文件下载器
wget [-b] url	-b表示后台下载，会创建一日志文件不断更新下载进度	url为下载链接

curl 命令发起网络请求
curl [-O] url	-O，当url为下载链接时可以用于下载文件

## 26.端口

IP只能确定计算机，通过端口才能锁定要交互的程序。

端口的划分
公认端口：1~1023，用于系统内置或常用知名软件绑定使用
注册端口： 1024~49151，用于松散绑定使用（用户自定义）
动态端口：49152~65535，用于临时使用（多用于出口， 即发送信息端口）

命令： nmap IP地址	查看指定IP对外暴露的端口，nmap需安装
netstat -anp | grep 端口号	查看本机端口的占用情况，通过grep命令进行关键词筛选，需安装net-tools

## 27.进程管理

程序在系统内运行后被注册为系统内的一个进程，并拥有独立的进程ID

ps [-e -f] 	查看进程信息，-e显示全部进程，-f以格式化形式展示
格式化展示的信息列表表头含义：
UID：进程所属用户ID	PID：进程号	PPID：启动该进程的进程号	C：cpu占用百分率	STIME：进程启动时刻	TTY：启动进程的终端序号，？表示非终端启动	TIME：占用cpu的总时长	CMD：进程对应名称或启动路径或启动命令

## 28.主机状态监控

top命令类似于任务管理器
iostat磁盘管理
sar查看网络情况

## 29.环境变量

 环境变量`PATH`记录一组目录(以:分隔)，当执行文件在当前工作目录下未找到时，系统便会在环境变量中查找。
export 变量名称=值	可以临时修改或添加变量（命令窗口重启便失效）
修改配置文件以永久修改环境变量： ~/bashrc（当前用户生效）	/etc/profile（全部用户生效）
在文件中添加`export PATH=$PATH:需要添加的路径`后保存即可，$PATH表示原环境变量的值。
**每次打开命令窗口，系统会读取配置文件以设置环境变量。也可通过命令`source 配置文件`来立即更新环境变量。**

## 30.压缩和解压

.tar文件，简单地将文件封装，没有太多的文件体积减小
.gz(也常见.tar.gz , gzip) ，通过gzip压缩算法将文件封装压缩

解压文件时，注意**同名文件覆盖**问题

`tar [-] 目录1、目录2...`
常用指令:-cvf	-zcvf 
-z一般处于第一个；**-f必须位于最后一个，后面接要压缩或解压的文件**；-C建议单独使用，和其他参数分开，后面接需解压到的目录。
![image-20241008222828253](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241008222828253.png)

zip [-r] 目录1、目录2...	-r表示目录中存在文件夹
unzip [-d] 需解压文件	-d用于指定解压到的路径

## 31.常用sudo命令（Ubuntu中）

`sudo -i`  切换为root用户
`sudo -u 用户名 命令` 切换到指定用户身份执行命令
`sudo -i -u 用户名` 切换到指定用户
`sudo -l` 查看当前用户的sudo权限
`sudo -s` 进入sudo会话，可以执行多次命令而不用再输入密码，exit退出。
`su - 用户名` 切换指定用户

12.su - root 输入密码123456（默认的）

临时切换到root用户

exit 切换回普通用户

13.用户组管理 需要root权限

groupadd 用户名（创建用户组）

groupdel 用户名（删除用户组）

14.getent group 查看当前系统有多少用户组



15.认知权限信息：

r (read)查看权限 w (write)修改权限 

x (execute)执行权限



16.chmod 命令 修改文件 文件夹 的权限信息（只有文件，文件夹 所属用户或者root用户可以修改）

语法：chmod ［-R］权限 文件或文件夹

例：chmod u＝rwx，g＝rx，o＝x hello.txt（将文件权限改为：rwxr-x--x）

例：chmod-R u＝rwx，g＝rx，o＝x test(将文件夹test以及内容全部权限设置为rwxr-x---x)



17.r记为4 w记为2 x记为1，可以有：

​       0:无任何权限，即 ---

​       1:仅有x权限，--x

​       2：仅有w权限，-w-

​       3:有w和x权限，-wx

​       4:仅有r权限，r--

​       5:有r和x权限，r-x

​       6:有r和w权限，rw-

​       7:有全部权限：rwx

​       所以751表示rwx（7）r-x(5) --x(1)



18.chown命令 修改文件 文件夹的所属用户和用户组 ，只适用root用户执行

语法：chown [-R] ［用户］［：］［用户组］文件或文件夹

-R，用户，用户组 都是选项

-R，对文件夹全部内容应用相同规则

：用于分隔用户和用户组

如：chown root hellow.txt(将hello.txt所属用户修改为root)

chown :root hellow.txt(将helow.txt所属用户组修改成root)

chown root:ittangmao hellow.txt(将hellow.txt所属用户修改为root，用户组修改为ittangamao）

chown -R root test (将文件夹test所属用户修改为root并对文件夹内全部内容应用同样规则

（总结，无： 只改所属用户，：右边有名称，改用户组，左右都有： 用户，用户组都改）



19.Linux快捷键：

ctrl+c 强制停止程序，退出命令输入

ctrl+d 退出或登出（不能用于vi/vim）

history 查看历史命令

history ｜grep ch（在历史记录中过滤带有ch命令）

！+命令的前缀，自动匹配上一次匹配的前缀命令

ctrl+r 输入内容去匹配历史命令

光标移动快捷键：

ctrl+a 调到命令开头

ctrl+e  跳到命令结尾

ctrl+键盘左键，向左跳一个单词

ctrl+键盘右键，向右跳一个单词

ctrl+l或者clear 清空终端内容（清屏）



20.yum命令 RPM（安装包）软件管理器，用于自动化安装配置Linux软件

语法：yum [-y] ［install ｜remove ｜search］软件名称

-y，自动确认，无需手动确认安装 卸载

instal安装 remove卸载 search搜索

（yum命令需要root权限 需联网）



21.systemctl命令控制：启动、停止、开机自启能够被syatemctl管理的软件，一般也称之为服务

语法：systemctl start ｜ stop｜ status ｜enable ｜disable 服务名

（启动/停止/查看状态/开启开机自启/关闭开机自启）



22.NetworkManager 主网络服务

network 副网络

firewalld 防火墙

sshd，ssh服务（Finalshell远程都玩Linux使用的就是这个服务）



23.ln命令 创建软连接（类似wind系统的快捷方式）

语法：ln -s 参数1 参数2

-s 创建软连接

参数1：被链接的文件或文件夹

参数2：要链接去的目的地

如：ln -s /etc/yum.conf ～/yum.conf

ln -s /etc/yum ～/yum



24.date命令 查看系统的时间

语法：date [-d] [+格式化字符串]

-d 按照给定的字符串显示日期，一般用于日期计算

格式字符串：

%Y 年 %y年份的后两位数（00..99）

%m月份（01..12） %d日（01..31）

%H小时（00..23）

%M分钟（00..59）

%S秒（00.60）

%s 自1970-01-01 00∶00∶00 UTC到现在的秒数



25.修改时区：1.先切换root权限

​        2.rm -f/etc/localtime （删除本地时间）

​        3.ln-s    /usr/share/zoneinfo/Asia/shanghai/etc/locatime (将这个文件链接为本地时间)

​        4. ntpdate -u ntp.aliyun.com(在阿里云网站配合ntp程序实时校准系统时间，需root权限)



26. 127.0.0.1 这个ip地址指代本机

0.0.0.0 特殊ip地址

可用于指代本机

也可以在端口绑定中用来确定绑定关系

在io地址限制中 表示所以ip



27.hostname 查看主机名字

hostnamectl set-hostname 新名字

（更改主机名字，需要root）