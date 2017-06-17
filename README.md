# Personal Less Library

> 自用Less库

[**Example**](http://htmlpreview.github.io/?https://github.com/baijunjie/less-lib/blob/master/index.html)

从2013年创建这个库，一点点的添加完善，目前功能已经基本稳定，现在它可以帮助我**快速**完成几乎所有的样式书写工作。对！就是**快速！**

### 为什么选择Less

Sass、Stylus、Less 如何选择？

这个问题是所有初学CSS预编译器的小伙伴最关心的问题。本人在工作中也使用过 Sass 和 Stylus，他们定义 Mixin 时非常便捷，语法类似于常见编程语言，并且有可以定义丰(鸡)富(肋)的函数供开发使用。而 Less 虽然也支持这些能力，但是写法却有些反人类，习惯了常规编程语言的人可能很难适应。

**一句话总结：**

- Sass - 写库便捷，调用繁琐
- Stylus - 写库...写不下去，调用懵逼
- Less - 写库繁琐，调用快捷

然而，我们的日常工作并不是去定义 Mixin，或者是去定义函数，我们的工作实际是需要书写大量页面样式代码，我们需要频繁的去调用之前定义的 Mixin 和函数。基于这个需求，个人而言， Less 无疑是我最佳的选择。

### Sass、Stylus、Less 能力对照表

下表是我在使用中发现的一些差异，这里只对有差异的能力进行比较，相同的能力不做对比。

| 能力       | Sass                          | Stylus                                   | Less                                     |
| -------- | ----------------------------- | ---------------------------------------- | ---------------------------------------- |
| 属性嵌套     | 有                             | 无                                        | 无                                        |
| 占位符选择器   | 有                             | 无                                        | 无                                        |
| 条件判断     | `@if`、`@else`                 | `if`、`else`                              | `when()`、`default()` （写复杂的条件判断会非常繁琐）     |
| 迭代       | `@for`、`@each`、`@while`       | `for in`                                 | `.loop()`（需要手动实现）                        |
| 字符串转换    | 加入引号、移除引号                     | 只能移除引号？                                  | 加入引号、移除引号                                |
| 传参       | 参数不能有`,`（但是CSS属性值有些是可以加`,`的啊） | 参数同样不能有`,`                               | 灵活传参，参数中有`,`时，可以使用`;`分隔参数。               |
| 定义函数     | 使用Sass定义的函数                   | 使用Stylus定义函数                             | 不但可以使用Less定义函数，还可以使用js定义函数（你没看错，v2.5+实现了这个能力） |
| 调用 Mixin | 繁琐的 `@include`                | 无参数时必须加`()`，如果 Mixin 和 CSS 属性名称相同，编译器会分不清楚你要写 CSS 还是要调 Mixin，甚至有些场景会出现循环调用的情况。松散的语法就是一把双刃剑，真是成也萧何，败也萧何。 | 怎么定义，就怎么调用，一切样式块都可以作为 Mixin 来调用，简直酸爽。    |
| 属性 merge | 无                             | 无                                        | 有（写库必备）                                  |
| 插入js表达式  | 无（想都不用想）                      | 无                                        | 有（理论上而言所有 Javascript 内置函数都可以在 Less 中调用）  |

### 最后

当然，Sass 和 Stylus 可能还有很多令人激动的能力，但是至少在我开发库的过程中并没有遇到必须要用的能力，相反基于 Less 的属性 merge 能力实现的一些功能在 Sass 和 Stylus 中是无法实现的。以上仅代表个人观点，如果有理解不到位的地方欢迎指正。