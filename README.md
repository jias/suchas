## 用一行代码说明`JS`的一个基础知识点或小技巧

对象实例的`__proto__`属性指向该实例的构造函数的`prototype`对应的对象。

```js
[].__proto__ === Array.prototype; // true
```

把类数组转换成数组

```js
Array.isArray([].slice.call(arguments)); // true
```

当索引源被重新赋值时...

```js
var a = {'a':'a'}; var b = a; a = {}; console.log(b); // {'a':'a'}
```

在`replace`中使用`$&`插入匹配到的字符串。

```js
'hi'.replace(/[hi]/g, '($&)');; // '(h)(i)'
```

数组中包含`undefined`值时，`join`操作后将转成空字符串。PS：`null`值同理。

```js
['a', undefined, 'b'].join(',') === 'a,,b'; // true
```

当`charAt`的参数指向字符串以外，`charAt`的返回值是空字符串。而`[]`方式取值，得到的是`undefined`。

```js
'0'.charAt(1) === ''; // true
'0'[1] === undefined; // true
```

可读性更强的打印JSON字符串的方法

```js
console.log(JSON.stringify({nickName:'fushan', realName:'gnosaij'}, null, 2));
```

眼见不一定为实，下面这些俄文字母，有些"坏人"会用它玩人，要小心！当然也可以用它"误导"别人。

```js
console.log('а' === 'a'); // false
console.log('о' === 'o'); // false
console.log('р' === 'p'); // false
console.log('х' === 'x'); // false
console.log('с' === 'c'); // false
console.log('у' === 'y'); // false

```

查看页面的最后构建(`build`)时间

```js
document.lastModified
```

用`ES6(ES2015)`对换两个变量的值如此简单

```js
[v1, v2] = [v2, v1];
```

还在用`'abc'.indexOf('a') > -1`吗？OUT!

```js
~'abc'.indexOf('a') && console.log('yes')
```

还在用`new Date().getTime()`吗？LOW!

```js
console.log(+new Date(), Date.now());
```

告诉IE使用最新的引擎渲染网页，`chrome=1`则可以激活`Chrome Frame`.

```html
<meta http-equiv="X-UA-Compatible" content="IE=Edge,chrome=1">
```



