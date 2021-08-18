##  JavaScript的历史

JavaScript是一种属于网络的高级脚本语言,已经被广泛用于Web应用开发,常用来为网页添加各式各样的动态功能,为用户提供更流畅美观的浏览效果。通常JavaScript脚本是通过嵌入在HTML中来实现自身的功能的。


JavaScript脚本语言具有以下特点:
1.脚本语言。JavaScript是一种解释型的脚本语言，C、C++等语言先编译后执行，而JavaScript是在程序的运行过程中逐行进行解释。
2.基于对象。JavaScript是一种基于对象的脚本语言，它不仅可以创建对象，也能使用现有的对象。
3.简单。JavaScript语言中采用的是弱类型的变量类型，对使用的数据类型未做出严格的要求，是基于Java基本语句和控制的脚本语言，其设计简单紧凑。
4.动态性。JavaScript是一种采用事件驱动的脚本语言，它不需要经过Web服务器就可以对用户的输入做出响应。在访问一个网页时，鼠标在网页中进行鼠标点击或上下移、窗口移动等操作JavaScript都可直接对这些事件给出相应的响应。
5.跨平台性。JavaScript脚本语言不依赖于操作系统，仅需要浏览器的支持。因此一个JavaScript脚本在编写后可以带到任意机器上使用，前提是机器上的浏览器支 持JavaScript脚本语言，JavaScript已被大多数的浏览器所支持。 [6]  不同于服务器端脚本语言，例如PHP与ASP，JavaScript主要被作为客户端脚本语言在用户的浏览器上运行，不需要服务器的支持。所以在早期程序员比较青睐于JavaScript以减少对服务器的负担，而与此同时也带来另一个问题，安全性。
而随着服务器的强壮，虽然程序员更喜欢运行于服务端的脚本以保证安全，但JavaScript仍然以其跨平台、容易上手等优势大行其道。同时，有些特殊功能（如AJAX）必须依赖JavaScript在客户端进行支持。


##  JavaScript诞生史

1994年，网景公司（Netscape）发布了Navigator浏览器0.9版。但是，这个版本的浏览器只能用来浏览，不具备与访问者互动的能力。

1995年Sun公司将Oak语言改名为Java，正式向市场推出，该公司许诺这种语言可以"一次编写，到处运行"。

网景公司的整个管理层，都是Java语言的信徒，Sun公司完全介入网页脚本语言的决策。因此，Javascript后来就是网景和Sun两家公司一起携手推向市场的，这种语言被命名为"Java+script"并不是偶然的。

1995年5月，网景公司做出决策，未来的网页脚本语言必须"看上去与Java足够相似"，但是比Java简单，使得非专业的网页作者也能很快上手。Brendan Eich被指定为这种"简化版Java语言"的设计师。

但是，他对Java一点兴趣也没有。为了应付公司安排的任务，他只用10天时间就把Javascript设计出来了。由于设计时间太短，语言的一些细节考虑得不够严谨，导致后来很长一段时间，Javascript写出来的程序混乱不堪。总的来说，他的设计思路是这样的：

　　（1）借鉴C语言的基本语法；

　　（2）借鉴Java语言的数据类型和内存管理；

　　（3）借鉴Scheme语言，将函数提升到"第一等公民"（first class）的地位；

　　（4）借鉴Self语言，使用基于原型（prototype）的继承机制。

所以，Javascript语言实际上是两种语言风格的混合产物----（简化的）函数式编程+（简化的）面向对象编程。这是由Brendan Eich（函数式编程）与网景公司（面向对象编程）共同决定的。


##    Javascript的10个设计缺陷

1. 不适合开发大型程序

Javascript没有名称空间（namespace），很难模块化；没有如何将代码分布在多个文件的规范；允许同名函数的重复定义，后面的定义可以覆盖前面的定义，很不利于模块化加载。

2. 非常小的标准库

Javascript提供的标准函数库非常小，只能完成一些基本操作，很多功能都不具备。

3. null和undefined

null属于对象（object）的一种，意思是该对象为空；undefined则是一种数据类型，表示未定义。

```
　　typeof null; // object

　　typeof undefined; // undefined
```

两者非常容易混淆，但是含义完全不同。

```

var foo;

　　alert(foo == null); // true

　　alert(foo == undefined); // true

　　alert(foo === null); // false

```


在编程实践中，null几乎没用，根本不应该设计它


4. 全局变量难以控制

Javascript的全局变量，在所有模块中都是可见的；任何一个函数内部都可以生成全局变量，这大大加剧了程序的复杂性。

```　
　a = 1;

　　(function(){

　　　　b=2;

　　　　alert(a);

　　})(); // 1

　　alert(b); //2

```

5. 自动插入行尾分号

Javascript的所有语句，都必须以分号结尾。但是，如果你忘记加分号，解释器并不报错，而是为你自动加上分号。有时候，这会导致一些难以发现的错误。

比如，下面这个函数根本无法达到预期的结果，返回值不是一个对象，而是undefined。

```
　　function(){

　　　　return
　　　　　　{
　　　　　　　　i=1
　　　　　　};

　　}

```

原因是解释器自动在return语句后面加上了分号。

```
　　function(){

　　　　return;
　　　　　　{
　　　　　　　　i=1
　　　　　　};

　　}

```

6. 加号运算符

+号作为运算符，有两个含义，可以表示数字与数字的和，也可以表示字符与字符的连接。

```
　　alert(1+10); // 11

　　alert("1"+"10"); // 110

```

如果一个操作项是字符，另一个操作项是数字，则数字自动转化为字符。

```
　　alert(1+"10"); // 110

　　alert("10"+1); // 101

```

这样的设计，不必要地加剧了运算的复杂性，完全可以另行设置一个字符连接的运算符。

7. NaN

NaN是一种数字，表示超出了解释器的极限。它有一些很奇怪的特性：

```
　　NaN === NaN; //false

　　NaN !== NaN; //true

　　alert( 1 + NaN ); // NaN

```

与其设计NaN，不如解释器直接报错，反而有利于简化程序。

8. 数组和对象的区分

由于Javascript的数组也属于对象（object），所以要区分一个对象到底是不是数组，相当麻烦。Douglas Crockford的代码是这样的：

```

　　if ( arr &&
　　　　typeof arr === 'object' &&
　　　　typeof arr.length === 'number' &&
　　　　!arr.propertyIsEnumerable('length')){

　　　　alert("arr is an array");

　　}

```

9. == 和 ===

==用来判断两个值是否相等。当两个值类型不同时，会发生自动转换，得到的结果非常不符合直觉。

```

　　"" == "0" // false

　　0 == "" // true

　　0 == "0" // true

　　false == "false" // false

　　false == "0" // true

　　false == undefined // false

　　false == null // false

　　null == undefined // true

　　" \t\r\n" == 0 // true

```

因此，推荐任何时候都使用"==="（精确判断）比较符。

10. 基本类型的包装对象

Javascript有三种基本数据类型：字符串、数字和布尔值。它们都有相应的建构函数，可以生成字符串对象、数字对象和布尔值对象。

```
　　new Boolean(false);

　　new Number(1234);

　　new String("Hello World");
```

与基本数据类型对应的对象类型，作用很小，造成的混淆却很大。

```
　　alert( typeof 1234); // number

　　alert( typeof new Number(1234)); // object

```
