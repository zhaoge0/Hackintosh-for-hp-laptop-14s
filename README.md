# Hackintosh-for-hp-laptop-14s
hp-14s笔记本安装macOS步骤简述

windows下：
1、下载macOS High Sierra 10.13.3 17D47 正式版 with Clover 4391原版镜像（https://blog.daliansky.net/）；

2、打开创建并格式化分区（windows自带），压缩得到一个40g以上的分区；

3、下载transmac，插入u盘将镜像写入u盘（至少8g）；

4、解压efi_fixed.zip,得到efi文件夹。

5、下载DiskGenious,挂载U盘efi分区，再挂载本地磁盘efi分区；

6、win+x - a,打开powershell，输入notepad，回车，文件-打开，把4中所得efi文件夹拖入u盘efi分区本地磁盘efi分区中，合并；

7、下载easyUEFI，在本地磁盘efi分区创建clover启动项；

8、重启，连按F9，进入引导项选择界面，按F10进入bios设置界面，关闭安全启动，提高u盘启动优先级；


macOS下：
9、重启进入u盘引导，进入macOS安装界面，选择磁盘工具将2所得分区进行分区或抹盘操作；

10、退出磁盘工具，选择安装macOS，等待安装，一段时间自带重启后，第二阶段安装；

11、配置用户设置，进入桌面；

12、替换SLE中的蓝牙驱动；

13、安装usbnet.pkg（usb网卡驱动可选）。



#附：可能用到的终端命令：

Windows下：
 diakpart
 sel disk <disk id>
 list part
 sel <partition id>
 assign letter = <letter>
 creat efi size = 300
  
macOS下：
 diskutil list
 diskutil mount
 sudo spctl --master-disable

 
