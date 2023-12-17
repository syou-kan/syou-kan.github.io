---
title: volantis配置3
headimg: https://static.dearxuan.com/background/pc/6.jpg
date: 2023-10-15
categories:
 - volantis
tags:
- 文章选项
- volantis
- 魔改
keywords:
- 文章样式
---





### 文章显示头图

在md文件头部添加

```md
---
title:
headimg: http:// #url
---
```

### 在文章内部不显示头图

```md
---
cover: false
---
```

### 首页文章不显示标题

在`source/_layout/_partial/post.ejs` 的判断区域新添加一个判断

```ejs
  // 文章不显示头图
  if (post.hideTitle && post.hideTitle === true) {
  showTitle = false;
}
```

`md`文件

```md
---
hideTitle: false #是否隐藏文章标题(可选)
---
```

### 是否隐藏文章摘要

```yml
# 文章布局
article:
  preview:
    # 如果不存在，则自动生成摘录(文章摘要)
    auto_excerpt: true # false, true
    # 隐藏摘录(文章摘要)
    hide_excerpt: true # false, true
```

