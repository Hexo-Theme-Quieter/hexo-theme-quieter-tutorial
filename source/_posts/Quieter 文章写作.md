---
title: Quieter 文章写作
date: 2024-11-13 19:01:00
tags:
  - Hexo
  - 帮助文档
series: 帮助文档
categories: 文档
cover: /images/covers/Quieter 文章写作.webp
typora-root-url: Quieter 文章写作
description: Quieter 主题的写作技巧。
toc: true
math: true
mermaid: true
APlayer: true
photoFigcaption: true
gallery: true
AES: true
---

# 前言

​	在这篇文章中，将为您展示 [Quieter](https://github.com/GZ-Metal-Cell/hexo-theme-quieter) 主题支持的写作样式。

# 正文

## 文本

​	主题推荐使用 [hexo-renderer-kramed](https://github.com/sun11/hexo-renderer-kramed) 作为渲染引擎。

---

`我是行内代码`

**我是粗体。**

*我是斜体。*

~~删除这段文字~~

---

​	在渲染文章时，Quieter 会自动将文章片段中的换号符转为四个 `&nbsp;`，如果不需要这个功能，可以在 **Quieter** 下的 `_config.yaml` 中关闭：

```yaml
# 自动将多个空格替换成对应的 &nbsp;
replaceSpacesWithNbsp: false
```

## 代码块

​	主题使用 `highlight.js` 进行代码高亮：

```C++
#include <iostream>

int main() {
    std::cout << "Hello, World!" << std::endl; 
    return 0;
}
```

```python
print("Hello, World!")
```

​	可以在文章开头设定代码块的显示形式：

```yaml
# 代码块自动关闭
highlight_shrink: true
# 代码块最大显示长度
highlight_height_limit: 480px
```

## 表格

| 名称 | 颜色 | 价格 |
| ---- | ---- | ---- |
| 香蕉 | 黄   | ￥2  |
| 苹果 | 红   | ￥3  |
| 青提 | 绿   | ￥6  |

## 列表

### 有序列表

1. 香蕉
2. 苹果
3. 青提

### 无序列表

- 香蕉
- 苹果
- 青提

## 图片

![picture](/images/random_covers/07.webp)

​	为了保证图片不占用较大的页面空间，主题默认规定图片大小：

```css
max-width: 100%;
max-height: 60vh;
```

​	主题默认开启 [fancybox](https://fancyapps.com/fancybox/)，这可以在 **Quieter** 下的 `_config.yaml` 中配置：

```yaml
# fancybox
fancybox:
    enable: true
    css: css/plugins/fancybox.css
    js: js/plugins/fancybox.umd.js
```

​	可以在文章开头设置：

```yaml
fancybox: false
```

​	从而关闭该页面的 fancybox。

​	也可以使用诸如下面的图片插入语句使得某张图片不参与 fancybox：

```html
<img no-fancybox src="xxx" alt="xxx"></img>
```

​	可以在文章开头进行如下设定使得文章图片下方附有对应的描述：

```yaml
photoFigcaption: true
```

## 数学公式

​	主题支持 Mathjax 或 Katex，需要在 **Quieter** 下的 `_config.yaml` 中配置（这里选择 Katex）：

```yaml
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

​	之后，需要在文章开头设置：

```yaml
math: true
```

​	下面是一个显示数学公式的示例：

```markdown
$$\int_{0}^{\infty} \frac{e^{-x^2}}{\sqrt{x}} , dx = \sqrt{\pi}$$
```

$$\int_{0}^{\infty} \frac{e^{-x^2}}{\sqrt{x}} , dx = \sqrt{\pi}$$

​	或

```markdown
得到这样的 $\sum_{n=1}^{\infty} \frac{1}{n^2} = \frac{\pi^2}{6}$ 行内数学公式。
```

得到这样的 $\sum_{n=1}^{\infty} \frac{1}{n^2} = \frac{\pi^2}{6}$ 行内数学公式。

## Mermaid

​	Quieter 适配并优化 [hexo-filter-mermaid-diagrams](https://github.com/webappdevelp/hexo-filter-mermaid-diagrams) 插件，在需要使用 Mermaid 的文章开头设置：

```yaml
mermaid: true
```

​	在**主题**下的 `_config.yaml` 中配置：

```yaml
# mermaid chart
# 可以配合（hexo-filter-mermaid-diagrams）
mermaid: ## mermaid url https://github.com/knsv/mermaid
  enable: true  # default true
  js: https://cdn.jsdelivr.net/npm/mermaid@11.4.0/dist/mermaid.min.js
  options: # find more api options from https://github.com/knsv/mermaid/blob/master/src/mermaidAPI.js
    #startOnload: true  // default true
```

​	效果：

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

## APlayer

​	Quieter 适配并优化 [hexo-tag-aplayer](https://github.com/MoePlayer/hexo-tag-aplayer/blob/master/docs/README-zh_cn.md) 插件，安装后请在**项目根目录**下的 `_config.yml` 将 aplayer 的预加载关闭：

```yaml
# 关闭 aplayer 预加载
aplayer:
    asset_inject: false
```

​	之后在需要使用 aplayer 的文章开头设置：

```yaml
APlayer: true
```

​	下面是一个在文章中插入音乐的示例：

```markdown
{% aplayer "No Happy Endings" "Tangerine Dream" "/musics/No Happy Endings.mp3" "/musics/No Happy Endings.webp" "" %}
```

​	效果：

{% aplayer "No Happy Endings" "Tangerine Dream" "/musics/No Happy Endings.mp3" "/musics/No Happy Endings.webp" "" %}

## 特殊 Tag

​	Quieter 支持一些 Markdown 以外的 Tag 语法，便于方便地加载一些特别的组件：

### AES 文章片段加密

​	Quieter 支持给文章的某个片段进行 AES 算法加密，需要安装 [crypto-js](https://www.npmjs.com/package/crypto-js) 插件，该功能与 [hexo-blog-encrypt](https://github.com/D0n9X1n/hexo-blog-encrypt)（全文加密）不冲突。

​	在需要进行文章片段加密的文章开头设置：

```yaml
AES: true
```

​	语法：

```markdown
{% AES passowrd, label %}
content
{% endAES %}
```

​	一个示例如下：

```markdown
{% AES 123456, "密码是 123456" %}
这是加密的内容！
{% endAES %}
```

​	效果：

{% AES 123456, "密码是 123456" %}
这是加密的内容！
{% endAES %}

### hide

​	搬运自 [Butterfly](https://butterfly.js.org/)。

#### hideInline

​	语法：

```markdown
{% hideInline content,display,bg,color %}
```

​	`content` 不能包含當引號，可用 `&apos;` 代替

​	示例：

```mark
苹果是{% hideInline "红色", display, #3c79b6, #fff %}的。
```

​	效果：

苹果是{% hideInline "红色", display, #3c79b6, #fff %}的。

#### hideBlock

​	语法：

```
{% hideBlock display,bg,color %}
content
{% endhideBlock %}
```

​	示例：

```markdown
{% hideBlock display, #3c79b6, #fff %}
这是按下按钮后显示的内容。
{% endhideBlock %}
```

​	效果：

{% hideBlock display,  #3c79b6, #fff %}
这是按下按钮后显示的内容。
{% endhideBlock %}

#### hideToggle

​	语法：

```markdown
{% hideToggle display,bg,color %}
content
{% endhideToggle %}
```

​	示例：

```markdown
{% hideToggle "点击展开" %}
这是隐藏的内容。
{% endhideToggle %}
```

​		效果：

{% hideToggle "点击展开" %}
这是隐藏的内容。
{% endhideToggle %}

#### Tabs

​	搬运自 [Butterfly](https://butterfly.js.org/)（这个主题又搬运自 [NexT](https://theme-next.js.org/)）。

​	语法：

```markdown
{% tabs id %}

<!-- tab 标签一 -->

content

<!-- endtab -->

<!-- tab 标签二 -->

content

<!-- endtab -->

{% endtabs %}
```

​	示例：

```markdown
{% tabs tab1 %}

<!-- tab 标签一 -->

    这是标签一里的内容。

<!-- endtab -->

<!-- tab 标签二 -->

    这是标签二里的内容。

<!-- endtab -->

{% endtabs %}
```

​	效果：

{% tabs tab1 %}

<!-- tab 标签一 -->

​	这是标签一里的内容。

<!-- endtab -->

<!-- tab 标签二 -->

​	这是标签二里的内容。

<!-- endtab -->

{% endtabs %}

### flink

​	在文章中显示友情链接：

​	示例：

```markdown
{% flink %}
- class_name: '写作'
  class_desc: '一些有助于写博客的网站'
  link_list:
    - name: 'emojiall'
      link: 'https://www.emojiall.com/zh-hans'
      avatar: 'https://gz-metal-cell.github.io/links/emojiall.webp'
      descr: '😍😉🤑🤭🤔😬😭'
    - name: 'Tinypng'
      link: 'https://tinify.cn/'
      avatar: 'https://gz-metal-cell.github.io/links/tinify.webp'
      descr: '压缩图片'
- class_name: '网站测速'
  class_desc: '测试网站性能如何？'
  link_list:
  - name: 'PageSpeed Insights'
    link: 'https://pagespeed.web.dev/'
    avatar: 'https://gz-metal-cell.github.io/links/pagespeed.webp'
    descr: '测速并提供优化建议'
  - name: 'Catchpoint'
    link: 'https://www.webpagetest.org/'
    avatar: 'https://gz-metal-cell.github.io/links/webpagetest.webp'
    descr: '测速并提供优化建议'
{% endflink %}
```

### 瀑布流相册

​	在需要进行使用瀑布流相册的文章开头设置：

```yaml
gallery: true
```

​	语法：

```markdown
{% gallery %}
 - {title: "图片 1", src: 图片链接}
 - {title: "图片 2", src: 图片链接}
 - {title: "图片 3", src: 图片链接}
 ...
{% endgallery %}
```

​	效果：

{% gallery %}

- {title: "图片 1", src: https://gz-metal-cell.github.io/2022/08/22/Diary-Garyton%E7%9A%846-8%E6%9C%88/0816_4.jpg}
- {title: "图片 2", src:  https://gz-metal-cell.github.io/2022/08/22/Diary-Garyton%E7%9A%846-8%E6%9C%88/0811_5.jpg}
- {title: "图片 3", src: https://gz-metal-cell.github.io/2022/08/22/Diary-Garyton%E7%9A%846-8%E6%9C%88/0809_1.jpg}

{% endgallery %}

### div

​	语法：

```markdown
{% div class, id %}
content
{% enddiv %}
```

​	这将会给 `conent` 外包一层 `<div class="class" id="id"></div>`，这在引入外部 css/js 文件时很有用。

​	示例：

```markdown
{% div subfields %}

{% div subfield %}

subfield 1.

{% enddiv %}

{% div subfield %}

subfield 2.

{% enddiv %}

{% enddiv %}
```

​	并引入对应的 css：

```css
.subfields {
    display: flex;
    border: 2px solid var(--border);
    transition: border 0.5s ease-in-out;
    margin: 5px auto;
}

.subfields > .subfield {
    flex: 1;
    transition: border 0.5s ease-in-out;
    padding: 0 10px;
}

.subfields > :not(:first-child).subfield {
    border-left: 1px solid var(--border);
}
```

<style>
    .subfields {
    display: flex;
    border: 2px solid var(--border);
    transition: border 0.5s ease-in-out;
    margin: 5px auto;
    }
    .subfields > .subfield {
        flex: 1;
        transition: border 0.5s ease-in-out;
        padding: 0 10px;
        /* align-content: center; */
    }
    .subfields > :not(:first-child).subfield {
        border-left: 1px solid var(--border);
    }
</style>

{% div subfields %}

{% div subfield %}

subfield 1.

{% enddiv %}

{% div subfield %}

subfield 2.

{% enddiv %}

{% enddiv %}

## 善于使用 html 语句进行写作

​	特殊的 Tag 可以以简便的语法实现特定的效果。然而，对于其他复杂的情况，要善于使用 html 语句进行写作。

​	示例：

```markdown
<marquee behavior="scroll" direction="right" scrollamount="15">
    <font color="red" size="4px">念桥边红药，年年知为谁生？</font>
</marquee>
```

​	效果：

<marquee behavior="scroll" direction="right" scrollamount="15"><font color="red" size="4px">念桥边红药，年年知为谁生？</font></marquee>

## 脚注

​	示例：

```markdown
引用自百度[^1]。
```

​	效果：

引用自百度[^1]。

[^1]: www.baidu.com

