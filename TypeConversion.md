## 类型转换

因为不同类型之间不允许进行运算，所以JS中经常会涉及类型转换的场景。

类型转换：不同原始数据类型之间互相转换

### 隐式类型转换

在部分运算场景中，JS会默认将数据进行类型转换，不需要主动对类型进行
转换。

#### 数字转换成字符

1. 数字转字符

当数字和字符相加的时候，运算会变成字符串拼接。

```
let a = 10;
let b = 'test';
console.log(a + b);  // '10test'
```

2. 字符转数字

当数字和字符相减的时候，字符（必须是数字型的字符）会变成数字参与运算。

```
let a = 10;
let b = '20';
console.log(a - b);  // -10
```

3. 布尔转换

布尔类型提供了两种状态：true 和 false

在我们在匹配判断的时候，在值为非0的情况下，大多数值都可以被识别为状态true。

```
if(true){  // 判断当前的状态为true
    console.log("可以被执行");
}

if(1){ // 判断当前状态为true
    console.log("可以被执行");
}
```

4. undefined和null弱相等

在JS中 undefined和null是弱相等的。（弱相等：非严格匹配）

```
if(undefined == null ){
    console.log("相等");
}
```

### 显式类型转换


[返回目录](https://github.com/hanchn/couse-of-Javascript)



