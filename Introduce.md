## 初识JS

Javascript早期被叫做LiveScript，因为当时Sun公司(被甲骨文公司收购)的
Java比较火。所以网景（Livescript的持有公司Netscape）为了蹭一波热度所
以将LiveScript改成Javascript。但是由于JavaScript也被甲骨文注册了，
所有我们一般称JavaScript为JS。

JS是一种解释型、弱类型语言，是基于ECMAScript标准的实现。

JavaScript创建者Brendan Eich，仅花了10天时间就把这么语言设计出来，主要
借鉴参考了Java语言的部分特性，仓促的设计使得这门语言在后期十几年一直饱受诟
病。   

不过话虽如此，JS也为web开发注入了新的生机，使得web开发生态变得非常有趣，JS
也因此成为了榜上有名比较火热的开发语言。

### 初识JS

JS需要在特定环境下进行编写，我们主要给大家介绍三种方式，如下：

#### 内嵌JS标签

内嵌JS标签主要是放置在静态页面中，并且在页面的任意位置放置成对的script标签
即可，例：

```
<script>
  // 在内部放置代码
</script>
```

#### 外链JS

外链JS通过链接的形式引入JS文件，依然是通过成对的script标签进行引入，例：

```
<script src="test.js"></script>
```

#### JS模块

ES6中新增了JS模块，我们可以通过模块的方式进行调用，本处只进行简单的示例演示，
后面小节会详细介绍到。

```
require test from 'test'
```


#### Hello World 

我们在静态页面中尝试输出一个简单的JS示例：

```
<script>
   alert('Hello World !');
</script>
```

[返回目录](https://github.com/hanchn/couse-of-Javascript)
[下一篇 注释](https://test.com)