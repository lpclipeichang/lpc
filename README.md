# linux基础及命令

## 一.计算机的基础
### &ensp;&ensp;&ensp;&ensp;1.计算机：俗称电脑，是一种能接收和存储信息，并按照存储在其内部的程序对海量数据进行自动、高速地处理，然后把处理结果输出的现代化智能电子设备。

### &ensp;&ensp;&ensp;&ensp;2.计算机硬件组成：1946年数学家冯·诺依曼于提出，计算机硬件由运算器、控制器、存储器、输入设备和输出设备五大部分组成。 
运算器的功能：运算器的主要功能是对数据进行各种运算。  

&ensp;&ensp;&ensp;&ensp;控制器的功能：是指按照预定顺序改变主电路或控制电路的接线和改变电路中电阻值来控制电动机的启动、调速、制动和反向的主令装置。

&ensp;&ensp;&ensp;&ensp;存储器的功能：存储器的主要功能是存储程序和各种数据，并能在计算机运行过程中高速、自动地完成程序或数据的存取。

&ensp;&ensp;&ensp;&ensp;输入设备的功能：输入设备是用户和计算机系统之间进行信息交换的主要装置之一。

&ensp;&ensp;&ensp;&ensp;输出设备的功能：输出设备的功能是将内存中计算机处理后的信息以能为人或其它设备所接受的形式输出。

## 二.Linux的版本

### 1.Linux的各个版本的差别
&ensp;&ensp;&ensp;&ensp;1.RedHat与Ubuntu的区别

&ensp;&ensp;&ensp;&ensp;这两个最大的区别在包管理模式上。  都是用的LINUX核心构架的。 

&ensp;&ensp;&ensp;&ensp;REDHAT主要集中在 企业级服务器版的制作 是推动LINUX商业化最成功的公司 REDHAT对应的桌面版制作 都是由Fedora社区研发。

&ensp;&ensp;&ensp;&ensp;Ubuntu桌面版 适合初学者 使用比较简单，桌面用户的首选ubuntu。

&ensp;&ensp;&ensp;&ensp;Linux 的发行版本可以大体分为两类，一类是商业公司维护的发行版本，一类是社区组织维护的发行版本，前者以著名的Redhat（RHEL）为代表，后者以 Debian为代表。

&ensp;&ensp;&ensp;&ensp;Redhat，应该称为Redhat系列，包括RHEL(Redhat Enterprise Linux，也就是所谓的Redhat Advance Server，收费版本)、Fedora Core(由原来的Redhat桌面版本发展而来，免费版本)、CentOS(RHEL的社区克隆版本，免费)。

&ensp;&ensp;&ensp;&ensp;Debian，或者称Debian系列，包括Debian和Ubuntu 等。Debian是社区类Linux的典范，是迄今为止最遵循GNU规范的Linux系统。

&ensp;&ensp;&ensp;&ensp;Ubuntu严格来说不能算一个独立的发行版本，Ubuntu是基于 Debian的unstable版本加强而来，可以这么说，Ubuntu就是一个拥有Debian所有的优点，以及自己所加强的优点的近乎完美的 Linux桌面系统。

&ensp;&ensp;&ensp;&ensp;Gentoo，伟大的 Gentoo是Linux世界最年轻的发行版本，正因为年轻，所以能吸取在她之前的所有发行版本的优点，这也是Gentoo被称为最完美的Linux发行版本的原因之一。

## 三.Linux的各种命令

1.命令的格式 

选项：用于启用或关闭命令的某个或某些功能短选项：-c  例如：-l, -h   

长选项：--word 例如：--all, --human-readable

2.简单命令

（1）关机：halt, poweroff

重启：reboot

-f: 强制，不调用shutdown

-p: 切断电源

关机或重启：shutdown

shutdown [OPTION]...  [TIME] [MESSAGE]

-r: reboot

-h: halt

-c：cancel

（2）ifconfig：查看当前系统的网络配置情况。

[root@CentOS6 ~]#`ifconfig`

>eth0      Link encap:Ethernet  HWaddr 00:0C:29:17:6B:D8  
          inet addr:192.168.230.132  Bcast:192.168.230.255  Mask:255.255.255.0
          inet6 addr: fe80::20c:29ff:fe17:6bd8/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:629 errors:0 dropped:0 overruns:0 frame:0
          TX packets:307 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:69399 (67.7 KiB)  TX bytes:35178 (34.3 KiB)

>lo        Link encap:Local Loopback  
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:12 errors:0 dropped:0 overruns:0 frame:0
          TX packets:12 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0 
          RX bytes:720 (720.0 b)  TX bytes:720 (720.0 b)

(3)whoami: 显示当前登录有效用户

[root@CentOS6 ~]#`whoami`
>root

(4)who: 系统当前所有的登录会话

[root@CentOS6 ~]#`who`

>root     tty1         2018-09-23 11:54 (:0)

>root     pts/0        2018-09-23 11:54 (:0.0)

>root     pts/2        2018-09-23 13:23 (192.168.230.1)

(5)w: 系统当前所有的登录会话及所做的操作

[root@CentOS6 ~]#`w`
 >16:26:50 up  4:33,  3 users,  load average: 0.00, 0.00, 0.00
USER     TTY      FROM              LOGIN@   IDLE   JCPU   PCPU WHAT
root     tty1     :0               11:54    4:33m  2.38s  2.38s /usr/bin/Xorg :0 -br -verbose -audit 4 -auth /var/run/gdm/auth-for-gdm-y8sDrQ/database -no
root     pts/0    :0.0             11:54    4:31m  0.00s  0.00s /bin/bash
root     pts/2    192.168.230.1    13:23    0.00s  0.13s  0.09s w

(6)nano 文本编辑

[root@CentOS6 ~]#`nano /etc/motd`

>                   _ooOoo_
>                  o8888888o
>                  88" . "88
>                  (| -_- |)
>                  O\  =  /O
>               ____/`---'\____
>             .'  \\|     |//  `.
>            /  \\|||  :  |||//  \
>           /  _||||| -:- |||||-  \
>           |   | \\\  -  /// |   |
>           | \_|  ''\---/''  |   |
>           \  .-\__  `-`  ___/-. /
>         ___`. .'  /--.--\  `. . __
>      ."" '<  `.___\_<|>_/___.'  >'"".
>     | | :  `- \`.;`\ _ /`;.`/ - ` : | |
>     \  \ `-.   \_ __\ /__ _/   .-` /  /
>======`-.____`-.___\_____/___.-`____.-'======
>                   `=---='
>
>
>^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

>           佛祖保佑       永不死机
>           心外无法       法外无心

(7)date:查看系统时间

[root@CentOS6 ~]#`date`

>Sun Sep 23 16:33:39 CST 2018
  
(8)hwclock:查看硬件时间

[root@CentOS6 ~]#`hwclock`

>Sun 23 Sep 2018 05:51:43 PM CST  -0.501962 seconds

(9)history查看历史命令

[root@CentOS6 ~]#`history`
>    1  nano /etc/profile.d/env.sh 

    2  exit
    3  cat /etc/gdm/custom.conf
    4  nano /etc/gdm/custom.conf
    5  exit
    6  ls
    7  nano /etc/motd
    8  exit
    9  nano /etc/motd

    -c: 清空命令历史

-d  offset: 删除历史中指定的第offset个命令 n: 显示最近的n条历史

-a: 追加本次会话新执行的命令历史列表至历史文件

-r: 读历史文件附加到历史列表

-w: 保存历史列表到指定的历史文件

-n: 读历史文件中未读过的行到历史列表

-p: 展开历史参数成多行，但不存在历史列表中

-s: 展开历史参数成一行，附加在历史列表后

  
  (10)hostname:查看主机名

  [root@CentOS6 ~]#`hostname`
>CentOS6.10

(11)runlevel:查看运行模式

[root@CentOS6 ~]#`runlevel`

>N 5

(12)free -h:显示以G为单位的内存使用

[root@CentOS6 ~]#`free -h`
>             total       used       free     shared    buffers     cached

Mem:          979M       577M       402M       2.7M        60M       182M

-/+ buffers/cache:       334M       645M

Swap:         2.0G         0B       2.0G

(13)tty:查看终端所在位置

[root@CentOS6 ~]#`tty`

>/dev/pts/2

(14)lsb_release -a:查看具体版本
[root@CentOS6 ~]#`lsb_release -a`
>LSB Version: 

   :base-4.0-amd64:base-4.0-noarch:core-4.0-amd64:core-4.0-noarch:graphics-4.0-amd64:graphics-4.0-noarch:printing-4.0-amd64:printing-4.0-noarch
Distributor ID: CentOS

Description:    CentOS release 6.10 (Final)

Release:        6.10

Codename:       Final

(15)lscpu:查看CPU

[root@CentOS6 ~]#`lscpu`

>Architecture:          x86_64

CPU op-mode(s):        32-bit, 64-bit

Byte Order:            Little Endian

CPU(s):                2

On-line CPU(s) list:   0,1

Thread(s) per core:    1

Core(s) per socket:    1

Socket(s):             2

NUMA node(s):          1

Vendor ID:             GenuineIntel

CPU family:            6

Model:                 94

Model name:            Intel(R) Core(TM) i7-6700HQ CPU @ 2.60GHz

Stepping:              3

CPU MHz:               2601.000

BogoMIPS:              5202.00

Hypervisor vendor:     VMware

Virtualization type:   full

L1d cache:             32K

L1i cache:             32K

L2 cache:              256K

L3 cache:              6144K

NUMA node0 CPU(s):     0,1

(16)df：找到光盘

[root@CentOS6 ~]#`df`

>Filesystem     1K-blocks    Used Available Use% Mounted on

>/dev/sda2       50264772 4366684  43338088  10% /

>tmpfs             501508      76    501432   1% /dev/shm

>/dev/sda3       30106576   44992  28525584   1% /data

>/dev/sr0         3897932 3897932         0 100% /media/CentOS_6.10_Final

(17)pwd:查看当前工作目录的完整路径

[root@CentOS6 ~]#`pwd`

>/root

(18)enable:查看内部命令

[root@CentOS6 ~]#`enable`

>enable .

enable :

enable [

enable alias

enable bg

enable bind

enable break

(19)type:查看当前命令是什么命令

[root@CentOS6 ~]#`type -a pwd `

pwd is a shell builtin

pwd is /bin/pwd

(20)hash:记录外部命令的路径

[root@CentOS6 ~]#`hash`

hits    command

>   1    /usr/bin/tty
   2    /bin/nano
   1    /usr/bin/lscpu
   1    /bin/hostname
   1    /bin/df
   1    /sbin/ifconfig
   1    /bin/date
   1    /sbin/runlevel
   1    /bin/uname
   1    /usr/bin/who
   1    /usr/bin/whoami
   1    /sbin/hwclock
   1    /usr/bin/w
   1    /usr/bin/free
   1    /usr/bin/lsb_release

   (21)alias:能把一个长命令改为短命令

   [root@CentOS6 ~]#`alias cdent="cd /etc/sysconfig/network-scripts/"`

[root@CentOS6 ~]#`cdent`

>[root@CentOS6 network-scripts]#

(22)screen:使用telnet或SSH远程登录linux时，如果连接非正常中断，重新连接时，系统将开一个新的session，无法恢复原来的session.screen命令可以解决这个问题。Screen工具是一个终端多路转接器，在本质上，这意味着你能够使用一个单一的终端窗口运行多终端的应用。

求助[root@CentOS7 ~]#`screen -S help`

查看用户[root@CentOS7 ~]#`screen -ls`

>There is a screen on:

        6214.help       (Attached)

1 Socket in /var/run/screen/S-root.

加入[root@CentOS7 ~]#`screen -x 3511.help `

[root@CentOS7 ~]#`ls `

anaconda-ks.cfg  Desktop  Documents  Downloads  fi  initial-setup-ks.cfg  

Music  Pictures  Public  Templates  Videos

退出[root@CentOS7 ~]#`exit`

screen -r:网断了可以重连

(23)bash快捷键

Ctrl + l	清屏，相当于clear命令

Ctrl + o	执行当前命令，并重新显示本命令

Ctrl + s	阻止屏幕输出，锁定

Ctrl + q	允许屏幕输出

Ctrl + c	终止命令

Ctrl + z	挂起命令

Ctrl + a	光标移到命令行首，相当于Home

Ctrl + e	光标移到命令行尾，相当于End

Ctrl + f	光标向右移动一个字符

Ctrl + b	光标向左移动一个字符

Alt + f	光标向右移动一个单词尾

Alt + b	光标向左移动一个单词首

Ctrl + xx 光标在命令行首和光标之间移动

Ctrl + u	从光标处删除至命令行首

Ctrl + k	从光标处删除至命令行尾

Alt + r      删除当前整行

Ctrl + w	从光标处向左删除至单词首

Alt + d	从光标处向右删除至单词尾

Ctrl + d	删除光标处的一个字符

Ctrl + h	删除光标前的一个字符

Ctrl + y	将删除的字符粘贴至光标后

Alt + c	从光标处开始向右更改为首字母大写的单词

Alt + u	从光标处开始，将右边一个单词更改为大写

Alt + l	从光标处开始，将右边一个单词更改为小写

Alt + t	交换光标处和之前的单词位置

Alt + N	提示输入指定字符后，重复显示该字符N次

注意：Alt组合快捷键经常和其它软件冲突

(24)help:帮助

[root@CentOS7 ~]#`help pwd`
>pwd: pwd [-LP]
    Print the name of the current working directory.
    
    Options:
      -L        print the value of $PWD if it names the current working
        directory
      -P        print the physical directory, without any symbolic links
    
    By default, `pwd' behaves as if `-L' were specified.
    
    Exit Status:
    Returns 0 unless an invalid option is given or the current directory
    cannot be read.

    


