---
title: 在CentOS上从零开始搭建博客
date: 2018-7-28 15:58:17
tags: 经验
---

## node.js的安装和配置
1. Centos下载node.js在Linux环境下预编译好的压缩文件
![nodejs安装](BlogGenerate/nodejs_1.png)
`wget https://nodejs.org/dist/v12.14.0/node-v12.14.0-linux-x64.tar.xz`
2. 解压node.js的压缩包
`tar -xvf node-v12.14.0-linux-x64.tar.xz`
`mv node-v12.14.0-linux-x64 nodejs12.14`
3. 建立软链接，node.js全局环境设置
`ln -s /root/software/nodejs12.14/bin/npm /usr/local/bin/`
`ln -s /root/software/nodejs12.14/bin/node /usr/local/bin/`
4. 修改~/.bashrc，最后一行加上如下命令
`export PATH=/usr/local/bin/:$PATH`
5. 查看node.js安装是否成功
`node -v`
`npm -v`
<!-- more -->
## hexo的安装和配置
1. node文件夹下安装cnpm
`npm install -g cnpm --registry=http://registry.npm.taobao.org`
`cnpm -v`
2. 建立软链接
`ln -s /root/software/nodejs12.14/bin/cnpm /usr/local/bin/`
3. node文件夹下安装hexo
`cnpm install -g hexo-cli`
4. 建立软链接
`ln -s /root/software/nodejs12.14/lib/node_modules/hexo-cli/bin/hexo /usr/local/bin/`

## 项目搭建
1. 创建项目的文件夹
`mkdir Blog`
2. 项目初始化
`hexo init`
3. 新建一个网页
`hexo new "我的第一个博客"`
4. 编辑文件 我的第一个博客.md
5. 项目生成
`hexo g或者hexo generate`
6. 项目启动
`hexo s或者hexo server`
7. 项目访问
`localhost:4000`
8. 项目清理
`hexo clean`

## 项目部署到github上
1. git的安装
`yum install git`
git version`
2. 配置git用户名
```shell
    git config --global user.name "username"
    git config --global user.email "XXXX@XX.com"
    git config --list
```
3. ssh生成公钥
```
ssh-keygen -t rsa -C "XXXX@XX.com"
秘钥存放路径：/root/.ssh/id_rsa
公钥：id_rsa.pub
私钥：id_rsa
```
4. 将公钥复制到github的SSH中
![github公钥](BlogGenerate/github_1.png)
5. 项目文件下安装hexo-deployer-git
`cnpm install --save hexo-deployer-git`
6. 在github上建一个仓库: 用户名.github.io
![github仓库](BlogGenerate/github_2.png)
7. 修改_config.yml文件
![git配置](BlogGenerate/github_3.png)
7. 将项目推送到github上
hexo deploy或者hexo d

## 项目中修改hexo的主题
1. 项目文件夹下克隆一个自己喜欢的主题
`git clone https://github.com/theme-next/hexo-theme-next themes/next`
`git clone http://github.com/litten/hexo-theme-yilia themes/yilia`
2. 修改_config.yml文件
![themes](BlogGenerate/theme_1.png)
3. 使用yilia注意事项
>在博客目录下执行:
`npm i hexo-generator-json-content --save`
>在根目录_config.yml里最后一行添加配置
![themes](BlogGenerate/theme_2.png)
4. 文章太长，截断按钮文字，写在.md文章当中
`<!-- more -->`
5. 修改more为不显示
>在主题目录下的_config.yml里修改配置

## 在hexo中添加图片
1. 项目文件下安装hexo-asset-image
`cnpm install hexo-asset-image --save`
2. 修改_config.yml文件
![image](BlogGenerate/image_1.png)
3. 更改项目下node_modules/hexo-asset-image/index.js文件
替换为本机内容如下的文件
```
'use strict';
var cheerio = require('cheerio');

// http://stackoverflow.com/questions/14480345/how-to-get-the-nth-occurrence-in-a-string
function getPosition(str, m, i) {
  return str.split(m, i).join(m).length;
}

var version = String(hexo.version).split('.');
hexo.extend.filter.register('after_post_render', function(data){
  var config = hexo.config;
  if(config.post_asset_folder){
    	var link = data.permalink;
	if(version.length > 0 && Number(version[0]) == 3)
	   var beginPos = getPosition(link, '/', 1) + 1;
	else
	   var beginPos = getPosition(link, '/', 3) + 1;
	// In hexo 3.1.1, the permalink of "about" page is like ".../about/index.html".
	var endPos = link.lastIndexOf('/') + 1;
    link = link.substring(beginPos, endPos);

    var toprocess = ['excerpt', 'more', 'content'];
    for(var i = 0; i < toprocess.length; i++){
      var key = toprocess[i];
 
      var $ = cheerio.load(data[key], {
        ignoreWhitespace: false,
        xmlMode: false,
        lowerCaseTags: false,
        decodeEntities: false
      });

      $('img').each(function(){
		if ($(this).attr('src')){
			// For windows style path, we replace '\' to '/'.
			var src = $(this).attr('src').replace('\\', '/');
			if(!/http[s]*.*|\/\/.*/.test(src) &&
			   !/^\s*\//.test(src)) {
			  // For "about" page, the first part of "src" can't be removed.
			  // In addition, to support multi-level local directory.
			  var linkArray = link.split('/').filter(function(elem){
				return elem != '';
			  });
			  var srcArray = src.split('/').filter(function(elem){
				return elem != '' && elem != '.';
			  });
			  if(srcArray.length > 1)
				srcArray.shift();
			  src = srcArray.join('/');
			  $(this).attr('src', config.root + link + src);
			  console.info&&console.info("update link as:-->"+config.root + link + src);
			}
		}else{
			console.info&&console.info("no src attr, skipped...");
			console.info&&console.info($(this));
		}
      });
      data[key] = $.html();
    }
  }
});
```
