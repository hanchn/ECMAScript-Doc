## Symbol

* 用于表示独一无二的变量名，而非变量值
* 表示独一无二的变量名（和const有区别，const表示不可修改的值）
* 可以显式转换成字符（toString）
* Symbol定义的变量名永远不相等
* 不能用点运算符调用对象（Symbol）属性名

### 定义Symbol类型的变量名

```
let s = Symbol();
console.log(typeof s); // 当前输出的是s变量名的类型
s = 'test';
console.log(typeof s); // 当前输出的是s变量值的类型
```

### Symbol.for

Symbol.for 接受一个字符串作为参数，然后搜索有没有以该参数作为名称的 Symbol 值。
如果有，就返回这个 Symbol 值，否则就新建并返回一个以该字符串为名称的 Symbol 值。

```
let s1 = Symbol.for('test');
let s2 = Symbol.for('test');
console.log(s1 == s2); // true


let s1 = Symbol('a');
let s2 = Symbol('b');
console.log(s1 == s2); // false
```

### Symbol属性成员

|属性名|释义|
|:--:|:--:|
|Symbol.for()|合并重复声明的Symbol属性|
|Symbol.keyFor()|返回一个已登记的 Symbol 类型值的key|
|Symbol.hasInstance|''|
|Symbol.isConcatSpreadable|''|
|Symbol.species|''|
|Symbol.match|''|
|Symbol.replace|''|
|Symbol.search|''|
|Symbol.split|''|
|Symbol.iterator|''|
|Symbol.toPrimitive|''|
|Symbol.toStringTag|''|
|Symbol.unscopables|''|
