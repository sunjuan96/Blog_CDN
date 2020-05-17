---
title: Vim
date: 2020-02-28 20:19:20
tags: 经验
---
## Vim使用前言
* Vim是Linux系统下的编辑器
* Vim适用于Linux用户，后端程序员，运维程序员
## 初识Vim
* Linux/Unix系统下本身就安装有Vim，Windows下可以安装Gvim
* Linux终端下输入vim，显示如下。:q退出vim
![VIM](LearningTools-Vim/vim_1.jpg)
#### Vim的四种模式介绍
Linux下输入vim 1.txt，进入1.txt可以进入normal模式
> normal模式，即标准模式。只能对文件进行浏览
* esc: 退出插其他模式，进入normal模式
* h: 左移光标
* l: 右移光标
> 编辑模式。在normal模式下按对应字母，进入对应的状态
* a : append模式, 在当前光标后面追加内容
* i : insert模式, 在当前光标前面插入内容
* o : open in a line below, 在当前光标下面空一行插入内容
* A : 光标跳到当前行最后一位置
* I : 光标跳到当前行最前一位置
* O : append a line above, 在当前光标上面空一行插入内容 
> 命令模式。在normal模式下按对应字母，进入对应的状态
* :w : 保存
* :q : 退出, 退出编辑，退出分屏等等
* :wq : write and quit, 保存并退出
* :vs : vertical split，竖分屏
* :sp : split, 横分屏
* :set nu: set number, 设置行号
> 可视化(Visual,v)模式。在normal模式下按对应字母，进入对应的状态
* v: 进入visual选择
* V: 进入行选择
* Ctrl+v: 进入块选择
* d: 批量删除
#### 插入模式小技巧
> 快捷键说明，编辑Txt的时候，同时适用于在终端下编辑命令时
* ctrl+h: 删除上一个字符
* ctrl+w: 删除上一个单词
* ctrl+u: 删除当前所在行
> 在终端下编辑命令时
* ctrl+a: 快速移动到开头
* ctrl+e: 快速移动在结尾
* ctrl+b: 光标往前移动一个字符
* ctrl+f: 光标往后移动一个字符
> 快速切换normal模式和插入模式
* ctrl+c或ctrl+[: 快速从插入模式切换到normal模式
* gi: 快速从normal模式切换到插入模式并且光标转到最后一次编辑的地方
* 映射方式：快速从normal模式切换到插入模式，替换Esc键
#### Vim的快速移动(normal模式)
> Vim的字符间快速移动的键位
* H(z左)J(下)K(上)L(右)
> Vim的单词间快速移动
* w/W: 移动到下一个word/WORD开头(word是指以非空白符分割的单词，WORD是指以空白符分割的的单词)
* e/E: 移动到下一个word/WORD结尾
* b/B: 回移到上一个word/WORD开头
> 行内搜索移动
* f{char}: 左(正)向搜索，移动到char字符上，使用;/,继续搜索
* t{char}: 左(正)向搜索，移动到char字符的上一个字符，使用;/,继续搜索
* F{char}: 右(反)向搜索，移动到char字符上，使用;/,继续搜索
* T{char}: 右(反)向搜索，移动到char字符的上一个字符，使用;/,继续搜索
> 水平移动：在一行上进行移动
* 0: 移动到该行首端的第一个字符
* ^: 移动到该行的第一个非空白字符
* $: 移动到该行的尾部
* g_: 移动到行位的非空白字符
> 垂直移动：在句子和段落之间进行移动
* (): 在句子之间移动
* {}: 在段落之间移动
* easymotion插件移动
> 页面移动
* gg/G: 移动到文件开头，ctrl+o快速返回
* H(head) M(middle) L(Lower)：分别跳转到屏幕的开头、中间和结尾
* ctrl+u: 向上翻页
* ctrl+f: 向下翻页
* zz: 把光标所在行放在屏幕中间
#### Vim快速的增删改查(normal模式)
* a/i/o: 增加
* x: normal模式下快速向后删除一个字符
* d: 配合文本对象快速删除一个单词，用法如下：
* daw: 删除一个单词，包括左右的空格
* diw: 删除一个单词，不包括周围的空格
* dd: 删除当前行
* dt{char}: delete to char，删除直到char字符的内容
* d0: 快速删除到行头
* d$: 快速删除到行尾
* x/d: 搭配数字执行多次删除
* 2x: 删除两个字符
* 3dd: 删除三行
* u: 恢复操作
* r(replace): r{char},用char替换当前内容
* c(change): 配合文本对象，进行快速修改
* s(substitute): 替换并进入插入模式
* S: 删除整行
* ct": 删除整个内容到双引号
* /: 前向搜索
* ?: 反向搜索
* n: 跳转到下一个匹配
* N: 跳转到上一个匹配
* *: 进行当前单词的前向匹配
* #: 进行当前档次的后向匹配
* :set hls: highlight search, 搜索结果高亮显示
* : set incsearch: 边搜索边高亮
#### Vim的搜索替换
* substitute命令，可以允许我们查找并且替换文本，支持正则表达式
* :[range] s[ubstitute]/{pattern}/{string}/[flags]
* range: 表示范围，如10,20表示10-20行，%表示全部。% s/self/this/g
* pattern: 表示替换的模式，正则表达式
* string: 替换后的文本
* flags: g(global)表示全局范围内执行；c(confirm)表示确认，可以确认或者拒绝修改；n(number)表示查询匹配的次数但是不替换
* 正则表达式： % s/\<function\>/fun/g, 用func替换单独的function，不替换包括单词中含有function的内容，比如def_function这种

#### Vim多文件操作
* Buffer: 缓冲区，Vim打开每一个文件都会将文件内容加载到缓冲区，之后的修改是针对内存中的缓冲区进行修改，不直接保存到文件，执行:w(write)后才会将修改内容写入到文件
* :ls // 列举当前缓冲区
* :b n // 跳转到第n个缓冲区
* :bpre // 跳转到上一个缓冲区
* :bnext // 跳转到下一个缓冲区
* :bfirst // 跳转到第一个缓冲区
* :blast // 跳转到最后一个缓冲区
* :b buffername // 用tab补全来跳转缓冲区
* :e ./a.txt // 打开某个缓冲区后在normal模式下打开另一个文件加载到缓冲区
* 窗口Windows: 可视化的分割区域；一个缓冲区可以分割成多个窗口，每个窗口也可以打开不同的缓冲区
* ctrl+w+s: 水平分割
* ctrl+w+v: 垂直分割
* ctrl+w+w: 窗口循环切换
* ctrl+w+h: 光标切换至左边窗口
* ctrl+w+j: 光标切换至下边窗口
* ctrl+w+k: 光标切换至上边窗口
* ctrl+w+l: 光标切换至右边窗口
* 在不同的窗口编辑同一个buffer，则每一个buffer都会同时被修改
* ctrl+w+H: 当前缓冲区至切换左边窗口
* ctrl+w+J: 当前缓冲区至切换下边窗口
* ctrl+w+K: 当前缓冲区至切换上边窗口
* ctrl+w+L: 当前缓冲区至切换右边窗口
* Tab标签页将窗口分组(不常用)，容纳一系列窗口
* :tabe[dit] file: 在新的标签页中打开file
* ctrl+w+t: 将当前窗口移动到一个新的标签页
* :tabc[close]: 关闭当前标签页以及其中的所有窗口
* :tabo[nly]: 只保留活动标签页，关闭其他所有标签页
* :tabn[ext] n: 切换到编号为n的标签页
* :tabn[ext]: 切换到下一个标签页
* :tabp[re]: 切换到上一个标签页
* :tabnew file：在新的标签页中打开file

#### Vim的文本对象Text Object
* 文本对象操作方式: [number]<command>[text object]
* number 表示次数，command是命令，d(elete),c(hange),y(ank)，text object操作的文本对象，单词w,居中s,段落p
* normal模式下的复制y(ank)粘贴p(ut)，可以配合文本对象使用
* insert模式下的复制粘贴,:set paste后使用ctrl+c和ctrl+v，:set nopaste恢复
* Vim的寄存器：Vim里操作的是寄存器而不是系统的剪贴板，使用d删除和y复制的内容都在某个寄存器中，x删除一个字符放到某个寄存器中，然后p粘贴。
* "{reg}指定寄存器: "ayiw复制一个单词到寄存器a中，"bdd复制一行到寄存器b
* 有名寄存器: a-z
* 复制专用寄存器: 0
* 系统剪贴板: +
* "%: 当前文件名
* ".: 删词插入的文本
* :echo has('clipborad') 输出为1表示支持系统剪贴板

#### Vim的宏
* q: 开始录制宏和结束录制宏
* q{register}: 选择要保存的寄存器，将录制的命令保存其中
* @{register}: 回放寄存器中保存的一系列命令
* 每一行加上双引号:方式一， qa 开始录制并保存到a，q退出录制，@a在每一行回放；进入visual模式执行normal模式下的命令G，:normal @a，则在所有行添加了双引号；方式二，normal I", normal A"

#### Vim的补全，2-8原则，度娘具体了解Vim的补全快捷键

#### Vim的配色修改
* vim a.txt b.py -o : 在两个窗口中打开a和b两个文件
* :colorscheme(可tab补全)，显示default
* :colorscheme A: 更改当前主题为名为A的主题
* 从网上下载配色主题，主题的github仓库具体的教程


## 个性化Vim，自定义Vim

## Vim插件的安装和使用





