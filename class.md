## class 

#### 基础结构

```
class Test {
  contructor(){

  }
}
```

#### 类的实例化和属性引用 

```
class Test {
  contructor(){

  }

  getSome(){

  }
}

Test.prototype = {
  contructor(){

  },
  getSome(){

  }
}
```

#### 类与不可被枚举

```
const args = {a: 1, b: 2, c: 3}
Object.keys(args);

class Test {
  _arg = '123'

  contructor(){

  }

  getSome(){

  }
}
Object.keys(Test);
```

#### 构造函数
如果没有显式定义，一个空的constructor()方法会被默认添加。
```
class Point {
}

// 等同于
class Point {
  constructor() {}
}
```

#### 属性定义

```
class Test {
  arg = 10
  contructor(){

  }

  getSome(){

  }
}
```

#### 取值存值

```
class Test {
  constructor() {

  }
  get prop() {
    return 'getter';
  }
  set prop(value) {
    console.log('setter: '+value);
  }
}

let test = new Test();

test.prop = 123;
// setter: 123

test.prop
```

#### 属性表达式

```
let funName = 'api'

class Test {
  constructor(){

  }

  [funName](){

  }
}
```

#### class 表达式

```
const MyClass = class Me {
  getClassName() {
    return Me.name;
  }
};
```

#### 静态方法

加上static关键字，就表示该方法不会被实例继承
```
class Foo {
  static classMethod() {
    return 'hello';
  }
}

Foo.classMethod() // 'hello'

```

静态属性目前还在提案阶段

```
class Foo {
  static prop = 1;
}
```

#### 私有属性
私有属性只能在类的内部使用，如果在类的外部使用，就会报错。
子类无法继承父类的私有属性

```
class Test {
  #count = 0
  contructor(){

  }

  #getSome(){

  }
}
```

#### in运算符

旧写法
```
class C {
  #brand;

  static isC(obj) {
    try {
      obj.#brand;
      return true;
    } catch {
      return false;
    }
  }
}
```

```
class C {
  #brand;

  static isC(obj) {
    if (#brand in obj) {
      // 私有属性 #brand 存在
      return true;
    } else {
      // 私有属性 #foo 不存在
      return false;
    }
  }
}
```

#### 静态块
静态块只运行一次，不支持return

```
class C {
  static x = ...;
  static y;
  static z;

  static {
    try {
      const obj = doSomethingWith(this.x);
      this.y = obj.y;
      this.z = obj.z;
    }
    catch {
      this.y = ...;
      this.z = ...;
    }
  }
}
```

#### 关于this

```
class Logger {
  printName(name = 'there') {
    this.print(`Hello ${name}`);
  }

  print(text) {
    console.log(text);
  }
}

const logger = new Logger();
const { printName } = logger;
printName(); // TypeError: Cannot read property 'print' of undefined
```

```
class Obj {
  constructor() {
    this.getThis = () => this;
  }
}

const myObj = new Obj();
myObj.getThis() === myObj // true
```

#### 继承

子类必须在constructor()方法中调用super()

```
class Point {
}

class ColorPoint extends Point {
  constructor(x, y) {
    super(); 
  }
}
```

#### 判断继承

Object.getPrototypeOf()方法可以用来从子类上获取父类。

```
class Point { /*...*/ }

class ColorPoint extends Point { /*...*/ }

Object.getPrototypeOf(ColorPoint) === Point
// true
```

super()只能用在子类的构造函数之中，用在其他地方就会报错

```
class A {
  p() {
    return 2;
  }
}

class B extends A {
  constructor() {
    super();
    console.log(super.p()); // 2
  }
}

let b = new B();
```