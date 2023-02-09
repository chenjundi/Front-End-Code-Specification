### 规范 Commit 的意义

无论是个人项目还是在团队协作中，commit message 都应该清晰明了，遵守一定规范（[Angular 规范](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#commits)）。

- 提供更明确的历史信息，方便浏览和判断提交目的
- 可以过滤某些不必要的提交，方便快速查找信息
- 自动化生成 Change log

### Commit 的格式

每次提交，commit message 都包括三个部分：header，body 和 footer。header 有一个特殊的格式包含有 type，scope 和 subject：

```
<type>(<scope>): <subject>  # header
<BLANK LINE>                # 空行
<body>                      # body
<BLANK LINE>                # 空行
<footer>                    # footer
```

header、body、footer 之间都要空一行，header 是必填项，scope 是选填项。commit message 的每一行的文字不能超过 `50` 个字符。这样子在 GitHub 和 Git 工具上更便于阅读。

##### type

type 用于说明 commit 的类别，必须为以下类型的一种：

type 用于说明 commit 的类别，一般常用的有下面几种标识：

`feat`：新功能（feature）
`fix`：修复 bug
`docs`：只是文档的更改（documentation）
`style`：不影响程序逻辑的代码修改（例如格式化、修改空白字符，补全缺失的分号等）
`refactor`：即不是新增功能，也不是修改 bug 的代码变动（一般指重构代码）
`perf`：提高性能的代码更改
`test`：新增测试用例或是更新现有测试
`revert`：回滚某个更早之前的提交
`build`：主要目的是修改项目构建系统（例如 glup，webpack，rollup 的配置等）的提交
`ci`：主要目的是修改项目继续集成流程（例如 Travis，Jenkins，GitLab CI，Circle 等）的提交
`chore`：不属于以上类型的其他类型（日常事务，例如对构建或者辅助工具的更改、生成文档等）

如果 type 为 feat 和 fix，则该 commit 将肯定出现在 Change log 之中。其他情况由你决定要不要放入 Change log，建议是不要。

##### scope

scope 用于说明 commit 影响的范围（比如数据层、控制层、视图层等等），当影响的范围有多个时候，可以使用 `*`。

##### subject

subject 用于对本次 commit 的简洁描述，不超过 `50` 个字符。
