---
title: 服务器使用
date: 2018-08-03 11:46:22
tags: 经验
---

### 服务器本地界面显示
1. 安装Xmanager
[百度云盘](https://pan.baidu.com/s/1hoBaAKVAI8YnMwMoVFNB1A) 提取码：bq4i
2. 软件配置
![Xmanger](SchoolServer/server_1.png)
![Xmanger](SchoolServer/server_2.png)
![Xmanger](SchoolServer/server_3.png)
![Xmanger](SchoolServer/server_4.png)
3. 配置Xshell
![XSell](SchoolServer/server_5.png)
![XSell](SchoolServer/server_6.png)
![XSell](SchoolServer/server_7.png)
![XSell](SchoolServer/server_8.png)
4. 打开MATLAB
在~/.bashrc中加入
`alias matlab=/raid/home/slf/install_path/matlab/bin/matlab`
![MATLAB](SchoolServer/server_9.png)

### 服务器后台运行代码
1. 开启一个后台
`screen -S xxx` //xxx代表后台窗口的名字
2. 快捷键退出后台但保持后台运行
`ctrl+a放开按d`
3. 再次进入后台程序
`screen -x xxx` //xxx代表后台窗口的名字
4. 永久退出后台程序
`screen -S xxx -X quit` //xxx代表后台窗口的名字

### 内网穿透，访问校园服务器

1. 外网主机登录命令`ssh -p 10001 slf@10.64.6.114`


