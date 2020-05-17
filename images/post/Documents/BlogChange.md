---
title: 博客进阶
date: 2018-7-29 15:58:17
tags: 经验
---

###  添加博客的头像和赞赏二维码
>+ 在项目目录themes/yilia/source下新建一个存放图片的文件夹，并将待添加的图片添加进去
`mkdir -r assets/imgs`
>+ 修改/themes/yilia/_config.yml文件
![修改赞赏二维码](BlogChange/yilia_1.png)
![修改头像](BlogChange/yilia_2.png)
>+ 修改版权声明：themes/yilia/layout/_partial/footer.ejs
![修改版权声明](BlogChange/yilia_3.png)
### 添加博客主页左边的内容添加tags
>修改/themes/yilia/_config.yml文件
![博客主页左边添加内容](BlogChange/yilia_4.png)
###  博文指定排序
>+ 修改项目下文件/node_modules/hexo-generator-index/lib/generator.js
![博文指定排序](BlogChange/yilia_4.png)
>+ 修改项目.md文件
![修改md文件](BlogChange/yilia_5.png)
