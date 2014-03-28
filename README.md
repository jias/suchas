# 一行代码

### 用一行代码说明javascript的一个基础知识点

对象实例的`__proto__`属性指向该实例的构造函数的`prototype`对应的对象。

    [].__proto__ === Array.prototype; // true

把类数组转换成数组

    Array.isArray([].slice.call(arguments)); // true

当索引源被重新赋值时...

    var a = {'a':'a'}; var b = a; a = {}; console.log(b); // {'a':'a'}
    
在`replace`中使用`$&`插入匹配到的字符串。

    'hi'.replace(/[hi]/g, '($&)');; // (h)(i)