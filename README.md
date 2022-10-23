# ddurl通过dd方式，将Linux服务器，安装为Windows系统的技术实践，含推荐的dd镜像源地址 2021-12-02
发表评论
段落1、需求描述，就是要一个可供远程的windows系统

1、太太发来指令，需要挂机一个学习类型的网站，网站主要是需要在线挂机，播放视频，挂学习时间

根据其需求，我们这里，使用PVE的环境，创建一台Windows系统，我们可以通过MSDN原版的ISO镜像方式安装系统。

我这里是PVE的虚机VPS环境，也可以通过dd的方式，正好可以来演示一下，一般可以在不提供Windows镜像的云服务器上，如何安装Windows系统。

2、购买的海外KVM架构的VPS服务器，商家只支持Linux系统的模板，也可以通过这个方法将当前的Linux系统，dd为Windows系统

段落2、比较靠谱的Windows镜像网站

推荐natee制作的windows系列镜像 网站 https://dd.nat.ee/ （可能已关闭，2022-03-08 更新）
推荐秋水逸冰制作的windows系统镜像 网站 https://teddysun.com/
段落3、使用的dd脚本为Vicer开发的

其 Github脚本InstallNET.sh的下载地址

安装环境

# apt-get install wget 

使用命令dd系统

# wget https://github.com/8730062/ddurl/blob/main/installNET

# bash InstallNET.sh -dd https://alist.lfcqjd.com/d/ali/Win10.vhd.gz
上面的这个地址，你们可以根据自己的需要，选择NATEE，或者秋水，或者其他的

SSD/NVMe盘的VPS性能比较好，一般dd速度比较快，dd安装完成，务必及时修改远程桌面的端口，默认账号的密码，默认账号的名称，非常重要，务必不要耽误太久，网络上很多扫3389的爆破机器人

判断dd是否完成，可以本地设置一个长ping，Windows命令为

ping -t xx.xx.xx.xx
段落4、附录

备注1，整个dd过程，是无值守的安装方式，一般正常情况都是一步到位，ping通之后一会儿，就可以使用远程桌面登录

备注2，在dd过程中，可以从你的VPS的供应商提供的HTML5/VNC里面观看自己VPS的dd的过程

备注3，一般1核/1GB内存/15G磁盘的配置，推荐dd为Windows7；2核/2GB内存/20GB磁盘的VPS配置，推荐dd为Windows10

2022-03-07 增补的章节

段落5、几个dd包下载的网站

A、系统dd包下载网 https://dd.1234234.xyz/

B、NATEE镜像站点 http://a.iplc.best/natee/

全过程的视频演示，YouTube：
<iframe width="625" height="351" src="https://www.youtube.com/embed/Cm8hxDhtjCs" title="000034  云VPS安装Windows，将一个Linux系统的主机，通过dd方式，安装为Windows系统的技术实践 20211202" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

