### 花括号

在大多数的 JavaScript 项目中，花括号以「Egyptian」风格书写，即左花括号与相应的关键词在同一行上，而不是新起一行。左括号前还应该有一个空格，如下所示：

推荐：

```
if (foo) {
  bar()
} else {
  baz()
}
```

不推荐：

```
if (foo)
{
  bar()
}
else
{
  baz()
}
```

### 单行代码块

在单行代码块中使用空格。

推荐：

```
function foo () { return true }
if (foo) { bar = 0 }
```

不推荐：

```
function foo () {return true}
if (foo) {bar = 0}
```

### 缩进

常见的缩进有三种：2 个空格、4 个空格、`Tab` 制表符。

本规范参考市面上优秀的开源项目，姑且约定使用 `空格` 来缩进，而且缩进使用两个空格。

对象字面量的键值缩进
对象字面量的键和值之间不能存在空格，对象字面量的冒号和值之间存在一个空格。

推荐：

```
const obj = { 'foo': 'haha' }
```

不推荐：

```
const obj = { 'foo' : 'haha' }
```

### 构造函数首字母大写

在 JavaScript 中 `new` 操作符用来创建某个特定类型的对象的一个实例，该类型的对象是由一个构造函数表示的。

由于构造函数只是常规函数，唯一区别是使用 `new` 来调用。所以我们约定构造函数的首字母要大写，以此来区分构造函数和普通函数。

推荐：

```
const fooItem = new Foo()
```

不推荐：

```
const fooItem = new foo()
```

### 拖尾换行

在非空文件中，存在拖尾换行是一个常见的 UNIX 风格，它的好处是可以方便在串联和追加文件时不会打断 Shell 的提示。在日常的项目中，保留拖尾换行的好处是，可以减少版本控制时的代码冲突。

推荐：

```
function func () {
  // do something
}
  // 此处是新的一行
```

不推荐：

```
function func () {
// do something
}
```

### 空行

空白行对于分离代码逻辑有帮助，但过多的空行会占据屏幕的空间，影响可读性。约定最大连续空行数为 `1`。

推荐：

```
const a = 1

const b = 2
```

不推荐：

```
const a = 1


const b = 2
```

### 变量声明

JavaScript 允许在一个声明中，声明多个变量。但我们约定在声明变量时，一个声明只能有一个变量。

推荐：

```
const a
const b
const c
```

不推荐：

```
const a, b, c
```

### 分号

每一个语句后面都应该有一个分号，即使它可以被跳过。

如果搞不清什么时候必须加分号，记得在以 `(`、`[`、`'`、`/`、`+`、`-`（即小括号、中括号、单引号、正则开头的斜杠、加号、减号）开头的语句前面都加上一个分号，否则可能得到非预想结果：

```
var a = 2
var b = 3
[a, b] = [b, a]
console.log(a)
console.log(b)
```

### 代码块空格

一致性是任何风格指南的重要组成部分。虽然在哪里放置块的开括号纯属个人偏好，但在整个项目中应该保持一致。不一致的风格将会分散读者阅读代码的注意力。

我们约定代码块前要添加空格。

推荐：

```
if (a) {
  b()
}

function a() {}
```

不推荐：

```
if (a){
  b()
}

function a(){}
```

### 函数声明的空格

本规范约定函数括号前不加空格。

推荐：

```
function func(x) {
  // ...
}
```

不推荐：

```
function func (x) {
  // ...
}
```

### 操作符的空格

操作符前后都需要添加空格。

推荐：

```
const sum = 1 + 2
```

不推荐：

```
const sum = 1+2
```

### 函数位置

如果你正在写几个「辅助」函数和一些使用它们的代码，我们约定先写调用代码，再写函数。

推荐：

```
// 调用函数的代码
let elem = createElement();
setHandler(elem);
walkAround();

// --- 辅助函数 ---
function createElement() {
  ...
}

function setHandler(elem) {
  ...
}

function walkAround() {
  ...
}
```

### 注释规范

#####单行注释
必须独占一行。`//` 后跟一个空格，缩进与下一行被注释说明的代码一致。

推荐：

```
// is current tab
const active = true
```

不推荐：

```
const active = true // is current tab
```

##### 多行注释

避免使用 `/*...*/` 这样的多行注释。有多行注释内容时，使用多个单行注释。

##### 特殊标记

有时我们发现某个可能的 bug，但因为一些原因还没法修复；或者某个地方还有一些待完成的功能，这时我们需要使用相应的特殊标记注释来告知未来的自己或合作者。常用的特殊标记有两种：

`// FIXME`：说明问题是什么
`// TODO`：说明还要做什么或者问题的解决方案
例如：

```
class Calculator extends Abacus {
  constructor () {
    super ()

      // FIXME: shouldn’t use a global here
      total = 0

      // TODO: total should be configurable by an options param
      this.total = 0
  }
}
```

##### 函数/方法注释

必须包含函数的说明，说明 what，而不是 how。
有参数和返回值时，必须有注释标志。
参数和返回值必须包含类型信息和说明。
当函数是内部函数，外部不可以访问时，可以使用 `@inner` 来标识。
推荐：

```
/**
 * Number formatting
 * like 10000 => 10k
 * @param {number} num
 * @param {number} digits
 * @return {string}
 */
function numberFormatter(num, digits) {
  const si = [
    { value: 1E18, symbol: 'E' },
    { value: 1E15, symbol: 'P' },
    { value: 1E12, symbol: 'T' },
    { value: 1E9, symbol: 'G' },
    { value: 1E6, symbol: 'M' },
    { value: 1E3, symbol: 'k' }
  ]
  for (let i = 0; i < si.length; i++) {
    if (num >= si[i].value) {
      return (num / si[i].value).toFixed(digits).replace(/\.0+$|(\.[0-9]*[1-9])0+$/, '$1') + si[i].symbol
    }
  }
  return num.toString()
}
```

##### 文件注释

用于告诉不熟悉这段代码的读者这个文件中包含哪些东西。
文件注释要标明作者、文件版本、创建/修改时间、重大版本修改记录。
推荐：

```
/**
 * @desc Description of file, its uses and information
 * @dependencies about its dependencies.
 * @author Author Name
 * @date 2020-12-29
 */
```
