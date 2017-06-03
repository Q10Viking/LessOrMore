---  

layout: post
title: "Hi,Jekyll"
categories: Jekyll
tag: [jekyll,blog]  
colorSet: #f00
date: 2017-06-02 17:24:05 +0800
banner: a simple,blog aware,static site generator 

---    

![index](http://oqyoidw83.bkt.clouddn.com/index.png)

#### 1.Jekyll定义    

> Jekyll is a parsing engine bundled as a ruby gem used to build staic websites from dynamic components such as templates,partials,liquid code,markdown,etc.    

Jekyll是一个解析引擎，通过将liquid,markdown等文件内容解析生成静态网页。这简化了我们写文章的复杂度。使得我们能够专注写文章，而不用操心文章怎样转换成html文件的形式，并且展示在网页上的过程。 



#### 2.Jekyll工作目录   

说明： 

> 从Jekyll 3.2开始，jekyll new 生成的静态网站的形式(默认是minima主题)，使用了gem-based themes来定义theme，这使得默认的目录更加轻便，同时也使得人更加困惑，因为它默认的将\_layouts,\_includes和\_sass存储在了theme-gem中   

 
``` 

├── about.md
├── assets
│   └── main.scss
├── _config.yml
├── Gemfile
├── Gemfile.lock
├── _includes
│   ├── disqus_comments.html
│   ├── footer.html
│   ├── google-analytics.html
│   ├── header.html
│   ├── head.html
│   ├── icon-github.html
│   ├── icon-github.svg
│   ├── icon-twitter.html
│   └── icon-twitter.svg
├── index.md
├── _layouts
│   ├── default.html
│   ├── home.html
│   ├── page.html
│   └── post.html
├── LICENSE.txt
├── _posts
│   └── 2017-06-03-welcome-to-jekyll.markdown
├── README.md
├── _sass
│   ├── minima
│   │   ├── _base.scss
│   │   ├── _layout.scss
│   │   └── _syntax-highlighting.scss
│   └── minima.scss
└── _site
    ├── about
    │   └── index.html
    ├── assets
    │   └── main.css
    ├── feed.xml
    ├── index.html
    └── jekyll
        └── update
            └── 2017
                └── 06
                    └── 03
                        └── welcome-to-jekyll.html  

```    

-  _site 是Jekyll将文件解析后，文件存放的地方，相当于我们访问域名的时候的根目录  
-  _post我们将写好的文章放到这个文件夹  
-  _layout存放生成网页的模板，一般都是用Liquid写成  
- _includes将一个网页的各个部分分解出来，放在这个文件中，提高代码的复用率  
- _sass里面的.scss文件在经过Jekyll处理后，会在_site中对应的位置生成.css文件来装饰我们的网页  
-  其他文件在生成静态网页的时候都会自动复制到_site中    

#### 3.Jekyll工作原理    

+ 解析markdown/textfile
+ 计算categories,tags  
+ 处理permalinks   
+ 从_layout中组织网页



#### 4.如何使用     

+ 如何发文章     
用**.md**的文件格式**markdown**语法来处理   
保存的格式: **yyyy-mm-dd-your-title.md**   
存放在**_post**文件夹中   
内容要有 [YAML Front Matter]( http://jekyllrb.com/docs/frontmatter/)


文章内容必须要有:    

```  

---
layout: post     <!--文章发布的形式-->
title: define your title  <!--标题-->
---  

```    

可选其他    

```  

---
layout: post
title: "Hi,Jekyll"
categories: Jekyll    <!--分类--><!--也可以定义多个分类[Jekyll,lessons]-->
tag: [jekyll,blog]  <!--定义多个标签-->
colorSet: 0f0       <!--自定义颜色-->
date: 2017-06-02 10:34:05 +0800   <!--发表的日期-->
banner: a simple,blog aware,static site generator   <!--banner栏-->
---  

* content     <!--添加这两栏，根据标题生成目录-->
{:toc}  

```      

+ _config.yml配置文件    

```  

name: Q10Viking
email: 1193094618@qq.com
author: 黄壮壮
url: http://q10viking.com
github: https://github.com/q10viking/
baseurl: ""
description: Actually, less is more!
meta_description: 黄壮壮,个人博客
banner: 非淡泊无以明志，非宁静无以致远  
color: 6C7A89  

```    

_config.yml中定义的属性都是默认的属性，通过**site**全局变量访问    

+ 补充说明    

```  

permalinks： /something/  <!--似乎在根目录才有效-->   

```    


+ 拓展菜单选项  
 + 可以在_include/header.html中添加想要的菜单项，然后在根目录中建立一个新的文件夹，用[Liquid](https://help.shopify.com/themes/liquid)语言编写自己需要的内容  

 + 第二种方式在_include/header.html的About中添加选项，在github中创建文件空间，然后处理号链接方式，（在github创建的文件空间中最好将分支设为gh-pages）。  




#### 5.Jekyll命令   
 
```  

jekyll --version   查看jekyll版本  
jekyll new .     在本目录下生成一个默认的blog  
jekyll build      生成静态网页   
jekyll serve     启动jekyll自带的服务程序  
bundle show minima  在文件中找到minima主题    

```  

#### 6.其他知识    

+ **div**对与整个网页的布局起着很重要的作用，在Mozilla Firefox中可以通过**开发者**==》**查看器**了解**盒子模型**,然后用**.css**文件对其处理    

+ 可以尝试注册一个[七牛云](https://www.qiniu.com/)使用它的云存储  


#### 7.参考    

> 感谢以下各个网站，组织，作者... ...的帮助==V==   


+ [Jekyll](https://jekyllrb.com/)    
+ [How Jekyll Works](http://jekyllbootstrap.com/lessons/jekyll-introduction.html)
+ [liquid](https://help.shopify.com/themes/liquid)    
+ [Jekyllthemes](http://jekyllthemes.org/)  
+ [Best Flats Color for UI Design](http://www.flatuicolorpicker.com/)
+ [Webjeda](https://blog.webjeda.com/)  
+ [Creating and Hosting a Personal Site on GitHub](http://jmcglone.com/guides/github-pages/)  
+ [How to get started with Jekyll on Ubuntu 16.04](https://askubuntu.com/questions/821657/how-to-get-started-with-jekyll-on-ubuntu-16-04)  
+ [How to create a website on Github Pages](https://www.youtube.com/watch?v=bwThn0rxv7M&list=PLm_Qt4aKpfKijgP0rDH7FSJOlS9IBGbT1&index=1)
