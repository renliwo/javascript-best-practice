# 1.文件
## 1.1 文件名

文件名如果是包含react则以**jsx**作为后缀，其他js文件以**js**结尾，json文件以**json**结尾。

普通文件名全部小写，react文件（jsx后缀的文件）首字母大写
## 1.2 文件编码
所有文件以utf-8编码。
# 2.变量
## 2.1 使用es6 的  const（prefer） 或者 let
## 2.2 使用es6 的 简写
### 2.2.1 对象的解构赋值

```
const {a,b} = {a:1, b:2}
console.log(a,b) // 1,2

// 数组不推荐使用解构
[...foo]   // preferred over Array.prototype.slice.call(foo)
[...foo, ...bar]   // preferred over foo.concat(bar)

```
### 2.2.2 默认值 =

```js
 function test(a = 0, b = true) {
 	if (b) return a;
 	return - a;
 }
```
### 2.2.3 对象方法的简写

```js
const a = {
 test() {
 }
}

```
### 2.2.4 使用属性简写

```js
function(a,b) {
   return {
   	  a,
   	  b
   }
}
```

### 2.2.5 尽可能使用箭头函数

### 2.2.6 使用模版字符串

# 3.注释
## 3.1多行注释

要写多行注释，除非是符合行业或项目约定的代码。

```js
/**
 * @param {string} required This parameter is always needed.
 * @param {string=} optional This parameter can be omitted.
 * @param {!Node=} node Another optional parameter.
 */
function maybeDoSomething(required, optional = '', node = undefined) {}
```
## 3.2 单行注释

尽量不要写单行注释，如果代码能准确表达意思，就让代码表达。
如何代码不能很好的表达做了什么，那么需要适当增加单行注释

```js
const a = 1; // a is constant

```

# 4.异常

# 5.处理警告
如果有需要不显示警告，请在**一定范围内**使用，在eslintrc配置文件中增加需要排除的文件和文件夹。

如果你在VSCODE问题面板中，或者eslint cli 中看到了你的
警告， 你需要以下三种方式的一种解决.

## 5.1 解决

## 5.2 增加TODO，并在之后尽快解决

## 5.3 如果是一个错误的，不合理的警告，提给主管，让其协助解决。

# 6.模块
## 6.1 添加模块
增加一个模块之前要确认没有可以重用的对应模块。（你可以在util或者components中翻一翻）。
## 6.2 引入模块
引入模块要遵循以下格式

每个类型之后空一行，类型包括但不限于 外部依赖（react，ant），actions，compoents，style, utils

```js
import React, { Component } from "react";
import PropTypes from "prop-types";

// components
import Select from "./components/Select";

// actions
import { fetchUser } from "../../actions/test";

```
# 7. 不要使用switch case， 用 hashmap 代替

# 8. 尽量不要使用this，如果确实需要，使用前需要bind，如果是jsx，要使用autobind-decorator

```jsx
import autobind from "autobind-decorator";
class Entry extends Component {
   @autobind
   handleClick() {
     this.setState({
       count: this.state.count ++
     })
   }
}

```


