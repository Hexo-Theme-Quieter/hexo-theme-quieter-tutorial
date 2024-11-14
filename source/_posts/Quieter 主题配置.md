---
title: Quieter 主题配置
date: 2024-11-14 12:24:00
tags:
  - Hexo
  - 帮助文档
series: 帮助文档
categories: 文档
cover: /images/covers/Quieter 主题配置.webp
typora-root-url: Quieter 主题配置
description: Quieter 主题配置。
toc: true
---

# 前言

​	**主题文件夹**下的 `_config.yml` 里的参数可以进行修改，从而配置主题。

# 正文

## 基本参数

| 名称            | 描述                             |
| --------------- | -------------------------------- |
| title           | 网站主页标题                     |
| suffix          | 网站标题后缀                     |
| author          | 作者名称（会显示在首页文章下面） |
| keyword         | 网站关键字                       |
| web_description | 网站描述                         |
| lang            | 网站语言                         |
| since_year      | 网站建站时间                     |
| logo            | 网站 LOGO（左上角的图标）        |

## about

​	`about` 属性可以设置个人信息，这将显示在侧边栏中：

```yaml
# 个人信息
about: 
    author: Zi-Zi
    portrait: 'https://gz-metal-cell.github.io/about/portrait.png'
    description: '不以物喜，不以己悲。'
```

## headers

​	`headers` 属性可以设置页面顶部的信息和图标：

```yaml
# 每个页面的展示的图标和一句话
headers:
    home:
        {
            message: "居然被你找到了这里！",
            icon: "/images/headers_icon/logo_white.webp",
        }
    categories:
        {
            message: "好像也没分几类",
            icon: "/images/headers_icon/categories.svg",
        }
    tags:
        {
            message: "这里是一些展示的标签",
            icon: "/images/headers_icon/tags.svg",
        }
    archives:
        {
            # 这里会替换掉两个变量{ year 年，number 总数 } 当然也可以不写这两个变量
            message: "居然一共才写了 number 篇文章！",
            message_month: "在 year 年 month 月里写了 number 篇文章！",
            message_year: "在 year 年里写了 number 篇文章！",
            icon: "/images/headers_icon/archives.svg",
        }
    galleries:
        {
            message: "有趣的相册~（施工中）",
            icon: "/images/headers_icon/galleries.svg",
        }
    links:
        {
            message: "一些神奇小网站~",
            icon: "/images/headers_icon/links.svg",
        }
    about:
        {
            message: "关于我",
            icon: "/images/headers_icon/about.svg",
        }
```

## 网站访问统计

​	`web_analytics` 可以对网站访问进行统计，支持不蒜子访问统计（在网页上显示访问量）和百度统计（后台查看访问信息）。

```yaml
# 网页访问统计
web_analytics:
    enable: true  # 需要改为 true
    busuanzi: true  # 不蒜子访问量统计
    baidu:  #（替换）百度统计的 Key，参见 https://tongji.baidu.com/sc-web/10000033910/home/site/getjs?siteId=13751376 代码获取中 hm.js? 后边的字符串
```

## 评论系统

​	Quieter 支持 `giscus` 和 `gitalk` 两种评论系统，需要自行在 github 上配置。

```yaml
# Giscus
# 配置方法详见 https://giscus.app/
giscus:
    enable: false
    repo: 
    repo_id: 
    category: Announcements
    category_id: 
    mapping: title
    strict: 1
    reactions-enabled: 1
    emit_metadata: 0
    input_position: bottom
    # loading: lazy

# gitalk 评论
gitalk:
    enable: false
    clientID: # （需要替换）GitHub Application Client ID.
    clientSecret: #（需要替换）GitHub Application Client Secret.
    repo: #（需要替换）GitHub repository.
    owner: #（需要替换）GitHub repository 所有者，可以是个人或者组织。
    admin: #（需要替换）GitHub repository 的所有者和合作者（对这个 repository 有写权限的用户）。
```

## bottom_icon

​	`bottom_icon` 属性控制侧边栏的个人介绍页面底部的信息：

```yaml
# 底部显示的图标（github 或者其他）
bottom_icon:
    # 可以多个
    - {
          # 描述名称
          name: "weibo",
          # 图标
          icon: "/images/bottom_icon/Weibo.webp",
          # 跳转链接
          link: "",
      }
    - {
          # 描述名称
          name: "tieba",
          # 图标
          icon: "/images/bottom_icon/Tieba.webp",
          # 跳转链接
          link: "",
      }
    - {
          # 描述名称
          name: "bilibili",
          # 图标
          icon: "/images/bottom_icon/Bilibili.webp",
          # 跳转链接
          link: "",
      }
    - {
          # 描述名称
          name: "github",
          # 图标
          icon: "/images/bottom_icon/github.webp",
          # 跳转链接
          link: "",
      }
```

## 特殊页面配置

​	下述的参数可以配置特殊页面的显示内容：

```yaml
# 归档页是否开启侧边栏
archive_aside: true
# 标签页是否开启侧边栏
tag_aside: true
# 标签页是否开启目录
archive_toc: true
# 标签页是否开启目录
tag_toc: true
```

## pagination

​	`pagination` 用于设置首页翻页按钮显示的上下文页数：

```yaml
# 翻页显示上下文页数，必须是一个自然数
pagination: 3
```

## search

​	Quieter 对 [hexo-generator-search](https://github.com/wzpan/hexo-generator-search) 进行了适配支持，如果本地搜索功能被正确地安装，将 `search` 值改为 `true` 即可在**归档**页处搜索文章：

```yaml
search: true
```

## lazyload

​	Quieter 对 [hexo-lazyload-image](https://github.com/Troy-Yang/hexo-lazyload-image) 进行了适配支持，如果图片懒加载功能被正确地安装，将 `lazyload` 值改为 `true` 即可开启该功能的适配：

```yaml
lazyload: false
```

## wordcount

​	Quieter 提供前端的字数统计功能，以如下方法打开：

```yaml
wordcount: true
```

## 空格替换

​	适配 [hexo-renderer-kramed](https://github.com/sun11/hexo-renderer-kramed) 插件。

​	默认情况下，在本地的 Markdown 打出的制表符/多个空格会被渲染成一个空格。将 `replaceSpacesWithNbsp` 设为 `true` 可将它们正确渲染：

```yaml
replaceSpacesWithNbsp: true
```

## fancybox

​	设置 fancybox。

​	主题中内嵌了 fancybox。

```yaml
# fancybox
fancybox:
    enable: true
    css: css/plugins/fancybox.css
    js: js/plugins/fancybox.umd.js
```

## 数学公式

​	mathjax 和 katex 用于显示数学公式，二者取其一。

​	主题中内嵌了 katex。

```yaml
mathjax:
    enable: false
    js: https://cdn.jsdelivr.net/npm/mathjax@4.0.0-beta.3/tex-mml-chtml.js

katex:
    enable: true
    css: /js/plugins/katex/katex.min.css # https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css
    js: /js/plugins/katex/katex.min.js # https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js
    auto_render: /js/plugins/katex/auto-render.min.js # https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js
    copy_tex:
        enable: true
        css: /css/plugins/copy-tex.css # https://cdn.bootcdn.net/ajax/libs/KaTeX/0.12.0/contrib/copy-tex.css
        js: /js/plugins/copy-tex.js # https://cdn.bootcdn.net/ajax/libs/KaTeX/0.12.0/contrib/copy-tex.js
```

## mermaid

​	[Mermaid](https://mermaid.nodejs.cn/) 允许用户用简便的代码绘制图表：

```yaml
mermaid: ## mermaid url https://github.com/knsv/mermaid
  enable: true  # default true
  js: https://cdn.jsdelivr.net/npm/mermaid@11.4.0/dist/mermaid.min.js
  options: # find more api options from https://github.com/knsv/mermaid/blob/master/src/mermaidAPI.js
    #startOnload: true  // default true
```

## default_cover

​	如果某个文章没有设置 `cover`，则会使用 `default_cover` 里的值作为封面：

```yaml
default_cover: "/images/random_covers/01.webp"
```

## random_top_img

​	如果某个文章没有设置 `top_img`，则会从 `random_top_img` 下面的列表中随机选取一张：

```yaml
random_top_img:
    - "/images/random_top_img/01.webp"
    - "/images/random_top_img/02.webp"
    - "/images/random_top_img/03.webp"
    - "/images/random_top_img/04.webp"
    - "/images/random_top_img/05.webp"
    - "/images/random_top_img/06.webp"
    - "/images/random_top_img/07.webp"
```

## inject

​	如果需要在网页中加入某些 html 语句而不修改主题内部代码，下述是一个简单的方式。

```yaml
# 所有网页中插入的 html 语句
inject: 
  head:
  bottom:
```

## icp

​	如果网站需要填写 ICP 备案信息，可在这里填写：

```yaml
icp:
    enable: false
    icon: 
    link: 
    text: 
```