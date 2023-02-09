### 文件模板

HTML5 文件模板：

```
<!DOCTYPE html>
  <html lang="zh-CN">
  <head>
    <meta charset="UTF-8">
    <title>HTML5 标准模版</title>
  </head>
  <body>
  </body>
</html>
```

移动端：

```
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport"
        content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, shrink-to-fit=no">
  <meta name="format-detection" content="telephone=no">
  <title>移动端 HTML 模版</title>

  <!-- S DNS预解析 -->
  <link rel="dns-prefetch" href="">
  <!-- E DNS预解析 -->

  <!-- S 线上样式页面片，开发请直接取消注释引用 -->
  <!-- #include virtual="" -->
  <!-- E 线上样式页面片 -->

  <!-- S 本地调试，根据开发模式选择调试方式，请开发删除 -->
  <link rel="stylesheet" href="css/index.css">
  <!-- /本地调试方式 -->

  <link rel="stylesheet" href="http://srcPath/index.css">
  <!-- /开发机调试方式 -->
  <!-- E 本地调试 -->

</head>
<body>
</body>
</html>
```

### 属性顺序

HTML 属性应当按照以下给出的顺序依次排列，确保代码的易读性。

> `id` > `class` > `name` > `data-*` > `src，for，type，href，value` > `title，alt` > `role，aria-*`

id 用于标识具体组件。
class 用于标识高度可复用组件。

### id 命名

元素 `id` 必须保证页面唯一。
`id` 建议单词全字母小写，单词间以 `-` 分隔。同项目必须保持风格一致。
`id、class` 命名，在避免冲突并描述清楚的前提下尽可能短。

### class 命名

`class` 必须单词全字母小写，单词间以 `-` 分隔。
`class` 必须代表相应模块或部件的内容或功能，不得以样式信息进行命名。
避免过度任意的简写。`.btn` 代表 `button`，但是 `.s` 不能表达任何意思。
基于最近的父 class 或基本（base） class 作为新 class 的前缀。

### name 命名

同一页面，应避免使用相同的 `name` 与 `id`。
`name` 一般与后端 `model` 中的字段名命名规则保持一致。
例如 Java 使用小驼峰命名法（camelCase），Python 使用下划线 `_` 连接两个小写单词。

### 标签类型属性

不需要为 CSS、JS 指定类型属性，HTML5 中默认已包含。
推荐：

```
<link rel="stylesheet" href="" >
<script src=""></script>
```

不推荐：

```
<link rel="stylesheet" type="text/css" href="" >
<script type="text/javascript" src="" ></script>
```

### 代码嵌套

元素嵌套规范，每个块状元素独立一行，内联元素可选。
推荐：

```
<div>
  <h1></h1>
  <p></p>
</div>
<p><span></span><span></span></p>
```

不推荐：

```
<div>
  <h1></h1><p></p>
</div>
<p>
  <span></span>
  <span></span>
</p>
```

段落元素与标题元素只能嵌套内联元素。
推荐：

```
<h1><span></span></h1>
<p><span></span><span></span></p>
```

不推荐：

```
<h1><div></div></h1>
<p><div></div><div></div></p>
```

### 注释规范

##### 单行注释

一般用于简单的描述，如某些状态描述、属性描述等。

注释内容前后各一个空格字符，注释位于要注释代码的上面，单独占一行。
推荐：

```
<!-- Comment Text -->
<div>...</div>
```

不推荐：

```
<div>...</div><!-- Comment Text -->

<div><!-- Comment Text -->
  ...
</div>
```

##### 模块注释

一般用于描述模块的名称以及模块开始与结束的位置。

注释内容前后各一个空格字符，<!-- S Comment Text --> 表示模块开始，<!-- E Comment Text --> 表示模块结束，模块与模块之间相隔一行。

推荐：

```
<!-- S Comment Text A -->
<div class="mod-a">
  ...
</div>
<!-- E Comment Text A -->

<!-- S Comment Text B -->
<div class="mod-b">
  ...
</div>
<!-- E Comment Text B -->
```

不推荐：

```
<!-- S Comment Text A -->
<div class="mod_a">
  ...
</div>
<!-- E Comment Text A -->
<!-- S Comment Text B -->
<div class="mod_b">
  ...
</div>
<!-- E Comment Text B -->
```

##### 嵌套模块注释

当模块注释内再出现模块注释的时候，为了突出主要模块，嵌套模块改用 <!-- /Comment Text -->。

注释写在模块结尾标签底部，单独一行。

```
<!-- S Comment Text A -->
<div class="mod-a">

  <div class="mod-b">
    ...
  </div>
  <!-- /mod-b -->

  <div class="mod-c">
    ...
  </div>
  <!-- /mod-c -->

</div>
<!-- E Comment Text A -->
```
