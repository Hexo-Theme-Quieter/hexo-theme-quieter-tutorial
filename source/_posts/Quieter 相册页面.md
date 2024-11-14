---
title: Quieter 相册页面
date: 2024-11-14 10:01:00
tags:
  - Hexo
  - 帮助文档
series: 帮助文档
categories: 文档
cover: /images/covers/Quieter 相册页面.webp
typora-root-url: Quieter 相册页面
description: Quieter 主题的相册页面的配置。
toc: true
---

# 前言

​	[Quieter](https://github.com/GZ-Metal-Cell/hexo-theme-quieter) 附带一个相册页面。

# 正文

## 关闭相册页面

​	如果不想要相册功能，可以在**主题文件夹下**的 `_config.yml` 下的将`galleries` 关闭：

```yaml
# 导航链接
menus_link:
    home: /
    categories: /categories
    tags: /tags
    archives: /archives
    # galleries: /galleries
    links: /links
    about: /about
```

## 配置相册页面

​	下面，我们通过一个示例来配置相册页面。

​	在 `source/` 下新建文件夹 `galleries`，如此构建 `galleries/` 下的文件结构：

- galleries
  - index.md
  - 相册集 1
    - index.md
    - 相册 3
      - index.md
    - 相册 4
      - index.md
  - 相册 2
    - index.md

​	设定 `galleries/index.md` 的头部内容：

```yaml
title: 相册
date: 2023-12-29 09:46:29
type: galleries
layout: galleries
layout_style: block
comments: true
galleries:
  - {title: "相册集 1", description: "这是相册 1 的示例。", cover: "XXX.jpg"} 
  - {title: "相册 2", description: "这是相册 2 的示例。", cover: "XXX.jpg"}
```

​	`layout: galleries` 表示页面的布局为 `galleries`（相册集）形式，有两种布局方式：

​	`layout_style: block` 和 `layout_style: card`。

​	`galleries:` 属性设置相册集指向的链接、描述、封面等。

---

​	同理，设置 `galleries/相册集 1/index.md` 的头部内容：

```yaml
title: 相册
date: 2023-12-29 09:46:29
type: galleries
layout: galleries
layout_style: card
comments: true
galleries:
  - {title: "相册 3", description: "这是相册 3 的示例。", cover: "XXX.jpg"} 
  - {title: "相册 4", description: "这是相册 4 的示例。", cover: "XXX.jpg"}
```

---

​	对于相册页面（`galleries/相册 2/index.md`、`galleries/相册集 1/相册 3/index.md`、`galleries/相册集 1/相册 4/index.md`），设置其内容：

```markdown
---
title: 相册标题
date: 2024-05-20 16:40:00
type: gallery
layout: gallery
description: 相册描述
comments: true
aside: true
---

{% gallery %}
 - {title: "图片 1", src: XXX.jpg}
 - {title: "图片 2", src: XXX.jpg}
{% endgallery %}
```

​	`layout: gallery` 表示这是一个相册页面，Quieter 将会引入相册页面的相关文件，其余正文内容与普通文章的排版方式基本一致。

​	可以使用 `{% gallery %}{% endgallery %}` 方便地创建瀑布流相册。

​	Quieter 的瀑布流相册对 [hexo-lazyload-image](https://github.com/Troy-Yang/hexo-lazyload-image) 插件做了适配优化。
