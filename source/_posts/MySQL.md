---
title: MySQL面试
headimg: https://static.dearxuan.com/background/pc/2.jpg
categories:
- 面试
tag:
- 面试八股文
- MySQL
- 八股文

---

`mysql`八股文第一部分

<!--move-->

### 除distinct外,数据库有哪些去重⽅式

除了使用 `DISTINCT` 关键字外，数据库中还有其他一些去重的方式，其中一些常见的包括：

<details><summary>GROUP BY</summary>
<pre><code>
SELECT column1, column2, COUNT(*)
FROM your_table
GROUP BY column1, column2;
</code></pre></details>

<details><summary>聚合函数（如MAX、MIN、AVG）</summary>
<pre><code>
SELECT MAX(column1), column2
FROM your_table
GROUP BY column2;
</code></pre></details>

<details><summary>使用窗口函数</summary>
<pre><code>
SELECT column1, column2
FROM (
    SELECT column1, column2, ROW_NUMBER() OVER (PARTITION BY column1 ORDER BY column2) as row_num
    FROM your_table
) as subquery
WHERE row_num = 1;
</code></pre></details>

### MySQL有哪些常⽤的查询语句

**SELECT：** 用于从一个或多个表中检索数据。

**ORDER BY：** 用于对结果进行排序。

**GROUP BY：** 用于将结果集按一列或多列进行分组。

**JOIN：** 用于在多个表之间建立关联

**DISTINCT：** 用于返回唯一不同的值。

```
https://hxd1-my.sharepoint.com/personal/onsimple_hxd1_onmicrosoft_com/Documents/%E8%87%AA%E5%B7%B1%E7%9A%84%E6%96%87%E6%A1%A3/%E5%9F%B9%E8%AE%AD/2386/%E8%A7%86%E9%A2%91/20230920_164524.mp4
```

```
https:/abc-my.sharepoint.com/personal/xxx_xxx_onmicrosoft_com/_layouts/15/download.aspx?UniqueId=xxx&SourceUrl=xxx
```

