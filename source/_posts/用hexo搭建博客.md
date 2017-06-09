# 一、安装NodeJS
- [官网下载](https://nodejs.org/en/)

# 二、安装 Git 
- `npm i git -g`

# 三、安装hexo
> 1、[官网](https://hexo.io/docs/)  
> 2、[安装教程](http://www.jianshu.com/p/31eb84182156)

- `npm install -g hexo`
- 常用命令
    - `hexo init`初始化博客项目文件目录
    - `hexo generate`(`hexo g`也可以) -- 生成静态页面
    - `hexo server`(`hexo s`也可以)  -- 启动本地服务，进行文章预览调试
    - `hexo new "My New Post"` 新建一篇博客

# 四、关联github 发布你的博客到gitpage

## (一)、流程

- _config.yml

```
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: https://github.com/520wsl/hexo.git
  branch: master0
```

- ==注意:后有空格==
- 然后登陆我的github 在github上建立一个仓库,`520wsl.github.io` 因为我的账号名是==520wsl==所以是这个
- `npm install hexo-deployer-git --save`
- `hexo deploy` 发布  -- 推送到GitHub
- 使用 `520wsl.github.io` 登录

## （二）、常用命令
    
1、`hexo deploy` 发布  -- 推送到GitHub

# 五、遇到的坑

## 1、修改根目录路径

### 问题：
    
    1、样式、图片、js等资源路劲不对
    
### 解决方案：
- _config.yml
```
# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'

url: http://yoursite.com
root: /hexo/
permalink: :year/:month/:day/:title/
permalink_defaults:
```

# 六、安装主题 shana

## 1、相关资料
- [hexo主题官网](https://hexo.io/themes/)
- [Shana主题Git资源](https://github.com/ShanaMaid/hexo-theme-shana)
- [安装教程--使用Hexo搭建博客（三），博客配置、主题和写作](http://www.jianshu.com/p/db7e64d86067)

## 2、安装
    git clone https://github.com/ShanaMaid/hexo-theme-shana themes/shana

## 3、配置
- 修改hexo根目录下的 _config.yml 


    修改博客目录D:\hexo\_config.yml中的theme属性，将其设置为shana。


```
# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
language: zh-CN
theme: shana
```

- 同时将themes/shana/_source/的tags和categories文件夹拷贝到hexo根目录下的source文件夹下
 
## 4、更新

    cd themes/shana
    
    git pull origin master

## 5、配置文件
```
# Header
menu:
  Home: /
  Archives: /archives
  Categories: /categories
  Tags: /tags
rss: /atom.xml

# Content
excerpt_link: Read More
fancybox: true

# Sidebar
sidebar: left
widgets:
- nav
- about

# display widgets at the bottom of index pages (pagination == 2)
index_widgets:
# - category
# - tagcloud
# - archive

# widget behavior
archive_type: 'monthly'
show_count: false

# Miscellaneous
google_analytics:
favicon: /favicon.png
twitter:
google_plus:
fb_admins:
fb_app_id:


# GalMenu - PC端右键调出，移动端长按
# galmenu决定是否开启
# mp3play决定是否开启音效
galmenu: true
mp3play: false
gaymenu_item:
- name: 首页
  url : /
- name: 标签
  url : /tags
- name: 分类
  url : /categories
- name: 归档
  url : /archives
- name: xxx
  url : xxxxxxxxx
- name: xxxx
  url : xxxxxxx

# 社交链接
social:
- url: http://github.com/ShanaMaid
  name: Github

# 友情链接
# name : url
link_title: 友情链接
links:
  ShanaMaid: http://blog.shanamaid.top/


# Sidebar Avatar
# in theme directory(source/images): /images/avatar.jpg
# in site  directory(source/uploads): /uploads/avatar.jpg
# 头像
avatar: https://avatars0.githubusercontent.com/u/20333903?v=3&s=460


# 网站统计
# 站长统计 填写id
# eg:　
# CNZZ: 123456789
CNZZ: 

# 评论
# 网易云跟帖APPkey
# 
netease: 

# leadcloud访问次数统计
# 
leancloud_visitors:
  enable: false
  app_id: 
  app_key: 
```

# 七、安装 Vateral 主题

# 相关资料
- [hexo主题官网](https://hexo.io/themes/)
- [Vateral主题git资源地址](https://github.com/moumao/hexo-theme-Vateral)

# 下载

    首先下载主题，解压好后放到themes目录

# 使用

    修改主题文件夹名称，将其改为 Vateral

# 配置

## 找到主题里的_config.yml文件
- seo：设置seo优化，keywords为网站搜索的关键字，description为网站搜索的网站介绍
- favicon：设置icon图标
- headbg：设置左侧抽屉中头像部分的背景图
- header：设置头像
- post_header：设置首页的标语部分，img：标语背景图，about：标语，url：为标语添加一个链接
- sns：添加社交账号链接，没有默认不填
- sidebar：导航栏配置，如果需要某项，use为ture，反之为false
- reading：设置自动生成摘要的字数

# ==*注：about friends photo要在hexo的文章目录下单独创建配置文件==
- photo:设置photo界面属性 ，name：相册名称 ，about：相册介绍

# about页面：
- 在 hexo 目录下的 source 文件夹内创建一个名为about的文件夹。

- 然后在文件内创建一个名为 index.md 的 Markdown 文件。

- 然后编辑里边的index.md文件
```
---
title: 关于
date: 2017-03-20 20:57:33
thumbnail: /images/random/bg4.jpg
layout: about
---
```
friends页面：

在 hexo 目录下的 source 文件夹内创建一个名为friends的文件夹。

然后在文件内创建一个名为 index.md 的 Markdown 文件。

在 index.md 文件内写入如下内容即可。

---
title: friends
date:
layout: friends
---
然后添加friends页面的数据

同样在在 hexo 目录下的 source 文件夹内创建一个名为 _data（禁止改名）的文件夹。

然后在文件内创建一个名为 friends.yml 的文件。

单个友情链接的格式为：

name:
    link: 此处为站点链接
    descr: "介绍"
如果想要添加多个友情链接，重复填写即可

photo界面：

在 hexo 目录下的 source 文件夹内创建一个名为 photo的文件夹。

然后在文件内创建一个名为 index.md 的 Markdown 文件。

在 index.md 文件内写入如下内容即可。

---
title: photo
date:
layout: photo
---
然后添加photo页面的数据    

同样在在 hexo 目录下的 source 文件夹内创建一个名为 _data（禁止改名）的文件夹。

然后在文件内创建一个名为 photo.yml 的文件。

单个图片的格式为：

name:
    large_link: /images/photo/1-large.jpg
    small_link: /images/photo/1-small.jpg
    very_small_link: /images/photo/1-very-small.jpg
    alt: "image 1"
*注：alt属性要对每照片编号

large_link: 原图 small_link: 小图片，建议正方形 very_small_link:模糊加载时首先加载的模糊图片

如果想要添加多个图片，重复填写即可

*注：_data文件夹不用重复创建

文章置顶功能

在需要置顶的文章头部加入如下即可置顶文章

up: true
本地搜索

使用本地搜索需要在hexo目录安装 hexo-generator-search 插件。

然后在 站点配置 文件中添加

search:
	path: search.xml
	field: all
计数统计

在主题配置文件中visitor属性设置为true即可开启全站的计数统计 在post_header属性中，设置visitor_front的值为访客数目的前缀，设置visitor_back的值为访客数目的后缀

博客运行时间统计

在_config.yml文件中的time属性设置为ture，并且设置begin_time属性为开始计时的时间

评论系统

*注：本主题暂时仅支持disqus，所以需要评论功能的话快翻墙注册一个账号吧~

在_config.yml文件中的comment属性，use设置为true，然后将shortname属性设置为你的disqus域名 格式如下：

comment:
    use: true
    shortname: yourname.disqus.com
如果不想使用则把use值设置为false即可

代码高亮

首先安装插件Hexo-Prism-Plugin npm i -S hexo-prism-plugin 在hexo的d_config.yml文件中修改增加如下：

prism_plugin:
  mode: 'preprocess'    # realtime：实时解析/preprocess：预处理
  theme: 'default'	# 高亮皮肤 默认为default 可选有default,coy,dark,funky,okaidia,solarizedlight,tomorrow,twiligh
  line_number: false    # default false 是否显示行数
要注意要修改配置文件中的默认配置highlight：

highlight:
 enable: false
 line_number: false
 auto_detect: false
 tab_replace:
重新生成静态文件这样就有代码高亮了~

ps：欢迎反馈高亮代码样式问题

文章配置

使用hexo命令生成一片新文章后，需要在md文件中进行如下配置

---
title: //文章标题
date: 2017-04-21 10:41:30
categories:
- //文章分类
tags: 
- //文章标签
- //文章标签
up: true //文章是否需要置顶，如果不需要此属性可以不写
thumbnail: //文章的图片url，如果不填则为默认图片
---