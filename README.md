## 用一行代码说明javascript的一个基础知识点或小技巧

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
console.log(JSON.stringify({name:’fushan’}, null, 2));
```

俄文的字母`а`，有些"坏人"会用它玩人，要小心！当然也可以用它"误导"别人。

```
console.log('а' == 'a'); // false

```
