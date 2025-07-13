---
title: 主题用法备忘
date: 2024-04-01
summary: 这是一篇 Markdown 文章的示例。展示了 Markdown 的语法和渲染效果。
category: 渲染测试
tags: [Markdown]
---

## 前置条件

- node 版本 >= 18.18.0
- pnpm 版本 > 8.1.0

## 安装

### 克隆仓库

登录 Github 账号，打开 [lxchapu/astro-gyoza](https://github.com/lxchapu/astro-gyoza)，点击右上角的 Fork 按钮，将仓库克隆到你自己的账号下。

复制这个仓库的地址，打开终端，使用 `git clone` 命令将仓库克隆到本地。

> 本项目推荐使用 pnpm 作为你的包管理器，如果你还没有安装 pnpm，请先安装 pnpm。

### 安装依赖

```sh
cd astro-gyoza
pnpm install
```

### 命令介绍

本地运行

```sh
pnpm dev
```

打包静态文件

```sh
pnpm build
```

本地预览

```sh
pnpm preview
```

### 配置项

本项目中的绝大部分配置都定义在 `src/config.json` 文件中。

你应该首先将 `site.url` 修改成自己的域名，避免导航错误。

以下是配置项的说明：

```json
{
  "site": {
    "url": "", // 网站地址
    "title": "", // 网站标题
    "description": "", // 通用的网站描述 SEO
    "keywords": "", // 通用的网站关键词 SEO
    "lang": "zh-CN", // 网站的语言
    "favicon": "", // 浏览器图标，存放在 public 目录下
    "appleTouchIcon": "" // 苹果设备图标，存放在 public 目录下
  },
  "author": {
    "name": "", // 作者名称
    "twitterId": "", // 推特账号 ID，以 @ 开头，用于 Open Graph
    "avatar": "" // 作者头像地址
  },
  // 首页 Hero 组件
  "hero": {
    "name": "", // 显示的名称
    "bio": "", // 一句话介绍
    "description": "", // 补充描述
    // 社交账号
    "socials": [
      {
        "name": "", // 社交平台类型
        "icon": "", // 社交平台图标
        "url": "", // 链接
        "color": "" // 图标颜色
      }
    ],
    "yiyan": "" // 显示一言
  },
  "color": {
    // 强调色，请填写 16 进制颜色值。每次会从中随机取出一组
    "accent": [{ "light": "", "dark": "" }],
    // 背景色
    "bg": {
      "primary": { "light": "", "dark": "" },
      "secondary": { "light": "", "dark": "" }
    },
    // 文字颜色
    "text": {
      "primary": { "light": "", "dark": "" },
      "secondary": { "light": "", "dark": "" }
    },
    // 边框颜色
    "border": {
      "primary": { "light": "", "dark": "" }
    }
  },
  // 顶部导航栏
  "menus": [
    {
      "name": "首页",
      "link": "/",
      "icon": "icon-pantone"
    }
  ],
  "posts": {
    "perPage": 10 // 每一页显示的文章数量
  },
  "footer": {
    "startTime": "" // 博客网站开始时间 请使用 ISO 格式
  },
  // Waline 评论系统，前往 https://waline.js.org/ 查看
  "waline": {
    "serverURL": ""
  },
  // 赞助
  "sponsor": {
    "wechat": "" // 微信赞赏码图片地址
  },
  // 如果需要使用网站数据统计，将 enable 修改为 true，并填写对应的配置
  "analytics": {
    "enable": false,
    // https://analytics.google.com
    "google": {
      "measurementId": ""
    },
    // https://umami.is/docs
    "umami": {
      "serverUrl": "",
      "websiteId": ""
    },
    // https://clarity.microsoft.com/
    "microsoftClarity": {
      "projectId": ""
    }
  }
}
```

## 部署

> 这里只介绍了 Vercel，你当然可以选择其他平台例如：Cloudflare Pages 或你自己的服务器。  
> 部署之前，确保你已经修改 `site.url`。

### 部署到 Vercel

登录 Vercel 账号，点击右上角的 Add new... 选择 Project。然后在 Import Git Repository 中选择刚刚 Fork 的仓库，点击 Import 按钮。

进入项目配置页面，直接点击 Deploy 按钮，静静等待部署完成就 👌 了。

Vercel 会为你分配一个域名，你可以在项目设置中设置自定义域名，更多操作请参考 Vercel 文档。

下面是在 Astro 中编写 Markdown 内容时，可以使用的一些基本 Markdown 语法示例。

## 标题

你应该避免在 Markdown 正文中重复创建文章标题，因为文章标题会根据 `frontmatter` 中 `title` 自动生成。

> 避免标题层级过深，一般到三级标题就够了。

# 一级

## 二级

### 三级 `inline code`

#### 四级

##### 五级

###### 六级

## 段落

Xerum, quo qui aut unt expliquam qui dolut labo. Aque venitatiusda cum, voluptionse latur sitiae dolessi aut parist aut dollo enim qui voluptate ma dolestendit peritin re plis aut quas inctum laceat est volestemque commosa as cus endigna tectur, offic to cor sequas etum rerum idem sintibus eiur? Quianimin porecus evelectur, cum que nis nust voloribus ratem aut omnimi, sitatur? Quiatem. Nam, omnis sum am facea corem alique molestrunt et eos evelece arcillit ut aut eos eos nus, sin conecerem erum fuga. Ri oditatquam, ad quibus unda veliamenimin cusam et facea ipsamus es exerum sitate dolores editium rerore eost, temped molorro ratiae volorro te reribus dolorer sperchicium faceata tiustia prat.

使用行尾使用两个空格进行段落内的换行

All work and no play makes Jack a dull boy.  
All work and no play makes Jack a dull boy.

## 图片

小尺寸的图片

![图片描述](https://picsum.photos/seed/picsum/250/400)

大尺寸的图片

![图片描述](https://picsum.photos/seed/picsum/1200/900)

带标题的图片

![图片描述](https://picsum.photos/seed/picsum/400/300 '图片标题')

## 强调

这是**重要内容**，这是*次要内容*

## 删除线

~~这是一段被删除的文本。~~

## 引用

The blockquote element represents content that is quoted from another source, optionally with a citation which must be within a `footer` or `cite` element, and optionally with in-line changes such as annotations and abbreviations.

> Tiam, ad mint andaepu dandae nostion secatur sequo quae.  
> **Note** that you can use _Markdown syntax_ within a blockquote.

嵌套的引用

> 引用
>
> > 嵌套的引用

带脚标的引用

> Don't communicate by sharing memory, share memory by communicating.<br>
> — <cite>Rob Pike[^1]</cite>

[^1]: The above quote is excerpted from Rob Pike's [talk](https://www.youtube.com/watch?v=PAAkCSZUG1c) during Gopherfest, November 18, 2015.

## 分割线

---

## 链接

这是内部链接 [Gyoza 使用指南](/posts/guide)

这是外部连接 [React **中文**文档](https://zh-hans.react.dev/)

自动渲染成连接 <https://github.com>

邮箱地址 <mail@example.com>

## 表格

设置单元格对齐

| Name  | Age |  Fruit |
| :---- | :-: | -----: |
| Bob   | 27  |  Apple |
| Alice | 23  | Banana |
| John  | 28  | Orange |

支持行内 Markdown

| Italics   | Bold     | Code   |
| --------- | -------- | ------ |
| _italics_ | **bold** | `code` |

表格溢出

| A                                                        | B                                                                                                             | C                                                                                                                                    | D                                                 | E                                                          | F                                                                    |
| -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------- | ---------------------------------------------------------- | -------------------------------------------------------------------- |
| Lorem ipsum dolor sit amet, consectetur adipiscing elit. | Phasellus ultricies, sapien non euismod aliquam, dui ligula tincidunt odio, at accumsan nulla sapien eget ex. | Proin eleifend dictum ipsum, non euismod ipsum pulvinar et. Vivamus sollicitudin, quam in pulvinar aliquam, metus elit pretium purus | Proin sit amet velit nec enim imperdiet vehicula. | Ut bibendum vestibulum quam, eu egestas turpis gravida nec | Sed scelerisque nec turpis vel viverra. Vivamus vitae pretium sapien |

## 代码块

### Syntax

we can use 3 backticks ``` in new line and write snippet and close with 3 backticks on new line and to highlight language specific syntac, write one word of language name after first 3 backticks, for eg. html, javascript, css, markdown, typescript, txt, bash

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Example HTML5 Document</title>
  </head>
  <body>
    <p>Test</p>
  </body>
</html>
```

```
const var text = "hello world"
```

## KaTeX 公式

使用 `$` 符号包裹公式生成行内公式，例如：$E = mc^2$。

使用 `$$` 符号包裹公式来生成独立公式。例如：

$$
e^{i\pi} + 1 = 0
$$

也可以使用代码块（` ```math `）的方式：

```math
\oint_{\partial V} \mathbf{E} \cdot d\mathbf{A} = \frac{Q}{\epsilon_0}
```

## List Types

### Ordered List

#### Syntax

```markdown
1. First item
2. Second item
3. Third item
```

#### Output

1. First item
2. Second item
3. Third item

### Unordered List

#### Syntax

```markdown
- List item
- Another item
- And another item
```

#### Output

- List item
- Another item
- And another item

### Nested list

#### Syntax

```markdown
- Fruit
  - Apple
  - Orange
  - Banana
- Dairy
  - Milk
  - Cheese
```

#### Output

- Fruit
  - Apple
  - Orange
  - Banana
- Dairy
  - Milk
  - Cheese

## Other Elements — abbr, sub, sup, kbd, mark

### Syntax

```markdown
<abbr title="Graphics Interchange Format">GIF</abbr> is a bitmap image format.

H<sub>2</sub>O

X<sup>n</sup> + Y<sup>n</sup> = Z<sup>n</sup>

Press <kbd><kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>Delete</kbd></kbd> to end the session.

Most <mark>salamanders</mark> are nocturnal, and hunt for insects, worms, and other small creatures.
```

#### Output

<abbr title="Graphics Interchange Format">GIF</abbr> is a bitmap image format.

H<sub>2</sub>O

X<sup>n</sup> + Y<sup>n</sup> = Z<sup>n</sup>

Press <kbd><kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>Delete</kbd></kbd> to end the session.

Most <mark>salamanders</mark> are nocturnal, and hunt for insects, worms, and other small creatures.

## Spoiler

```md
||hide content||
```

正常情况下，该内容会隐藏 ||hide content||，鼠标悬浮时才会显示。

Gyoza 选择 font-class 的方式引用图标。这些图标大部分来源于 [Remix Icons](https://remixicon.com/)，并且在 [iconfont](https://www.iconfont.cn/) 上进行管理和导出。

下图展示了项目中的所有图标：

![所有图标](https://s2.loli.net/2024/05/08/mbdT5HqYMEajyRG.webp)

当你在添加首页显示的社交账号时，你可能会想要使用这些图标。在对应的配置项中填写图标下面有 `icon-` 前缀的名称即可。

如果是在组件中使用图标，可以按照如下方式：

```jsx
<i className="iconfont icon-xxx"></i>
```

## 为什么不是 SVG 图标？

你可能看到很多的项目在使用 [iconify](https://iconify.design/)。iconify 是一个开源图标集，包含超过 20 万个图标，提供了多种框架的引入方式。Astro 中也有对应的插件 astro-icon 可以使用（如果对此感兴趣，可以查看他们的[文档](https://github.com/natemoo-re/astro-icon)）。

我在项目中也尝试使用过 iconify，但是出于以下几个原因，我最终还是转向了 font-class 的方式：

- 由于项目中同时使用了 Astro 和 React，而在 Astro 组件和 React 组件中使用 iconify 图标的方式是不同的，这会导致代码中不得不存在两种使用方式。
- iconify 在加载时需要请求它的服务器，~~我会担心请求失败~~，虽然这种担心是多余的。
- 有一个功能是我会在渲染文章时往 markdown 中注入一些图标，例如外部链接尾部的图标，iconify 想要做到这一点并不方便。
- 在 HTML 中直接嵌入 SVG icon 的方式并不优雅，使用 font-class 只需要对应的类名，感觉相较而言最终的 HTML 体积小一点，页面加载会快点。我还没有做过具体的测试，但是至少我会尽量避免页面中出现大量的 SVG 仅仅只是作为图标使用。
- 该项目中用到的图标并不多，主要是一些常用的社交账号的图标，供自定义联系方式时使用。我希望所有图标集中在一起管理，这样更方便一点。

我必须要承认，目前的图标方案并不优雅，每当图标集合发生修改时我都需要更新对应的字体文件和 CSS 文件。而且其他人想要管理图标集合也变得困难。

也许我会在未来尝试其他方式，例如 [@iconify/tailwind](https://github.com/iconify/iconify/tree/main/plugins/tailwind)，如果你有更好的方案，也欢迎给我留言。

## 自定义图标

如果你想要替换 iconfont 的图标，请修改以下文件：

```text
public/fonts/iconfont.ttf
public/fonts/iconfont.woff
public/fonts/iconfont.woff2
src/styles/iconfont.css
```

注意，这将会替换掉项目中使用的所有图标，所以请确保你知道自己在做什么。

## Codepen

```md
::codepen{#gOyLepE author="lxchapu"}
```

::codepen{#gOyLepE author="lxchapu"}

## YouTube

```md
::youtube{#BuKft9LpL_0}
```

::youtube{#BuKft9LpL_0}

## Bilibili

```md
::bilibili{#BV1Mx4y1Y7pJ}
```

::bilibili{#BV1Mx4y1Y7pJ}
