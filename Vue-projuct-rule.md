### Vue 项目基础规则

JavaScript 语句后不加分号
缩进使用两个空格
常用的命名规范：

`camelCase`（小驼峰式命名法 —— 首字母小写）
`PascalCase`（大驼峰式命名法 —— 首字母大写）
`kebab-case`（短横线连接式）
`Snake`（下划线连接式）

### 工程目录

全局通用的组件放在 `/src/components/` 下。
页面/视图组件放在 `/src/views/` 下。
全局公共函数方法（多于三个文件以上引用）放在 `/src/utils/` 下。
当页面文件具有私有组件、指令、过滤器时，则建立一个与页面同名的目录，页面文件更名为 `index.vue`，然后在该目录下创建私有 `./components` 等文件夹。
例如：

```
src/
├── App.vue
├── main.js
├── assets
├── router                         # 路由
├── store                          # vuex状态管理
├── components                     # 公共组件
├── utils                          # 全局公共函数方法
└── apis                           # 全局公共接口
    ├── login                      # 对应views目录
    │   └── index.vue
    └── profile                    # 对应views目录
        └── index.vue
└── views                          # 页面/视图
    ├── login
    │   ├── components             # 私有组件
    │   └── index.vue
    └── profile
        ├── components             # 私有组件
        └── index.vue
```

### 命名规范

##### 通用文件与文件夹

1. 项目名
   全部采用小写方式，以短横线分隔。例如：`my-project-name`。

2. 目录名
   有复数结构时，要采用复数命名法。例如：`docs`、`assets`、`components`、`directives`、`mixins`、`utils`、`views`。

3. 图像文件名
   全部采用小写方式， 优先选择单个单词命名，多个单词命名以下划线分隔。

```
├── banner_sina.gif
├── menu_aboutus.gif
├── menutitle_news.gif
├── logo_police.gif
├── logo_national.gif
├── pic_people.jpg
├── pic_TV.jpg
```

4. CSS 文件名
   全部采用小写方式， 优先选择单个单词命名，多个单词命名以短横线分隔。

```
├── normalize.less
├── base.less
├── date-picker.scss
├── input-number.scss
```

5. JavaScript 文件名
   全部采用小写方式， 优先选择单个单词命名，多个单词命名以短横线分隔。

```
├── index.js
├── plugin.js
├── util.js
├── date-util.js
├── account-model.js
├── collapse-transition.js
```

##### Vue 组件命名

1. 单文件组件名
   文件扩展名为 `.vue` 的 `single-file components`（单文件组件）。单文件组件名应该始终是单词大写开头（PascalCase）。

推荐：

```
src/
├── MyComponent.vue
```

2. 组件内部参数命名

   组件名应该始终是多个单词，应该始终是 PascalCase 的。根组件 App 以及 <transition>、<component> 之类的 Vue 内置组件除外。这样做可以避免跟现有的以及未来的 HTML 元素相冲突，因为所有的 HTML 元素名称都是单个单词的。

推荐：

```
export default {
  name: 'ToDoList',
  // ...
}
```

3. 模板中组件
   对于绝大多数项目来说，在单文件组件和字符串模板中组件名应该总是 PascalCase 的，但是在 DOM 模板中总是 kebab-case 的。

推荐：

```
<!-- 在单文件组件和字符串模板中 -->
<MyComponent/>

<!-- 在 DOM 模板中 -->
<my-component></my-component>
```

4. 自闭合组件
   在单文件组件、字符串模板和 JSX 中没有内容的组件应该是自闭合的 —— 但在 DOM 模板里永远不要这样做。

推荐：

```
<!-- 在单文件组件和字符串模板中 -->
<MyComponent/>

<!-- 在所有地方 -->
<my-component></my-component>
```
