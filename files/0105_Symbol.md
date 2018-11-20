## Symbol

JS中属性名太多的情况下，容易产生重名冲突，于是就有了Symbol类型。

Symbol和const常量定义倒是有些类似，两者都表示**唯一**，两者的约束对象不同。

Symbol用于约束属性名，const用于约束属性值。


### Symbol 类型定义

1. 基础定义

```
let a = Symbol(); 
let b = Symbol();

// a 不等于 b 
```

2. 赋名定义

```
let a = Symbol('a'); 
let b = Symbol('b');

// a 不等于 b 
```

3. 对象赋值

```
let a = Symbol('a');
let obj = {};
    obj [a] = 10;
```

### Symbol.for 和 Symbol.keyFor

Symbol在每次使用的时候都会重新创建新的属性名，如果我们想要使用Symbol类型的同名的话可以使用Symbol.for。

Symbol.for 会检测给定的key是否存在，如果存在则直接使用已经存在的值。

1. Symbol.for定义唯一键（属性名）

```
let v = Symbol.for('a');
```

2. 获取Symbol键（属性）名

```
let v = Symbol.for('a');
console.log(Symbol.keyFor(v))
```