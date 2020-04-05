---
date: 2017-04-09T10:58:08-04:00
description: "The Grand Hall"
featured_image: "/images/Pope-Edouard-de-Beaumont-1844.jpg"
tags: ["scene"]
title: "I:v2ray"
---

V2ray是继Shadowsocks(R)后又一个体验很棒、功能非常强大的科学上网工具，近年来受到网友的广泛关注和喜爱。本教程
详细介绍V2ray的特点，安装和配置过程，让读者能迅速上手和使用V2ray。在本文基础上，建议网友继续阅读 v2ray高级技
巧：流量伪装，体验更稳的上外网方式。v2ray客户端下载请访问：
https://github.com/Cenmrev/V2RayX/releases/download/v1.2.1/V2RayX.app.zip。

一.服务端安装和配置

首先你需要有一台位于境外的服务器，一顿操作服务器完成之后，打开mac终端使用ssh root@ip 然后输入密码进入服务器
1.下载go.sh：
wget https://install.direct/go.sh
2.然后执行：
sudo bash go.sh
3.安装完之后，使用以下命令启动 V2Ray：
sudo systemctl start v2ray

二.客户端安装

1.V2RayX下载客户端软件
https://github.com/Cenmrev/V2RayX/releases/download/v1.2.1/V2RayX.app.zip
下载完成后解压如果是mac用户需要把解压后的软件拖到Appaction中
更全面的下载地址，没尝试不知道可不可用
https://tlanyan.me/v2ray-clients-download/

2.V2Ray一键安装脚本 自带图形化界面控制面板
在之前进入的ssh境外服务器中复制以下命令开始安装
wget -N --no-check-certificate https://raw.githubusercontent.com/FunctionClub/V2ray.Fun/master
/install.sh  && sudo bash install.sh
如果运行以上命令时，出现找不到wget的英文提示，则表示系统没有安装wget，根据系统不同，选择以下命令安装：
CentOS：
yum -y install wget
Ubuntu/Debian：
apt-get -y install wget

3.V2Ray安装接近完成时，会提示输入用户名、密码、控制面板端口，可随意设置正常来说，V2Ray已经安装成功了，可以尝试
在浏览器打开控制面板地址，我目前没有出现特殊打不开的情况
    地址：http://服务器ip:面板端口号
    输入设置好的用户名密码
注意：
如果打不开可以复制下面命令
pip install Flask-BasicAuth

4.以上命令运行完成后，我们再启动面板。服务器输入以下命令，然后选择1回车。如下图，提示V2ray.fun started，即表示
启动成功。
v2ray
注意：
    如果出现权限问题请 sudo 一下（我这里提示已经启动啦）

5.浏览器输入服务器IP 刚才设置的端口，访问V2Ray控制面板，输入用户名和密码登录，登录成功后的界面如下图所示：
各项连接参数都显示在运行状态菜单。最下面的Vmess链接和二维码图片，都可以用于客户端连接。

进入控制面板网页版-》选择修改连接-》协议类型：vmess-》主机端口号：可以自行修改刷新-》UUID：可以刷新-》加密方式：
auto自动选择-》传输方式：TCP

6.完成之后，去控制面板 “运行状态” 下载配置文件，下载之后文件类型改为config.json 格式

7.点击桌面右上角的V2RayX图标，会弹出如下菜单，选择PAC Model -》点击Configure进入设置：
Local Socks5 Prot：默认（自行设置） ，UPD勾选， LAN选择性勾选
Local Http prot：默认
DNS：localhost
V2ray servers：选择导入把刚刚控制面板里的config.json导入到其中各个参数于控制面板对应，其中alterld如果没有的话
默认或者些100 ，level 0， NetWork选择 tcp 
点击ok 选择右上角图标load core 启动v2ray 至此完成

2Ray控制面板打不开解决办法

V2Ray.fun控制面板比较直观好用，但是部分情况下，会出现安装完成后，打不开控制面板的情况。其实前文已经提到过解决办法，这里再重复一次，方便单独出现此问题的朋友：
终端连接VPS购买的境外服务器，分别输入以下命令运行：
1. pip install Flask-BasicAuth
2. v2ray
3. 1



