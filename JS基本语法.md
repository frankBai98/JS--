# JS基本语法(入门级)
## 一、什么是表达式和语句
  1、语句和表达式的区别在于，前者主要为了进行某种操作，一般情况下不需要返回值；后者则是为了得到返回值，一定会返回一个值。

  2、一般情况下，每一行就是一个语句。语句（statement）是为了完成某种任务而进行的操作，比如下面就是一行赋值语句。
``` javascript
var a = 1 + 3; 
```
这条语句先用var命令，声明了变量a，然后将1 + 3的运算结果赋值给变量a。

1+3叫做表达式(expression),指一个为了得到返回值的计算式。

3、语句以分号结尾，一个分号就表示一个语句结束。多个语句可以写在一行内。
``` javascript
var a = 1 + 3 ; var b = 'abc';
```
## 二、变量
1、变量的含义

变量是对“值”的具名引用。变量就是为“值”起名，然后引用这个名字，就等同于引用这个值。变量的名字就是变量名。
* 注意，JavaScript 的变量名区分大小写，A和a是两个不同的变量。

2、变量提升(hoisting)

JavaScript 引擎的工作方式是，先解析代码，获取所有被声明的变量，然后再一行一行地运行。这造成的结果，就是所有的变量的声明语句，都会被提升到代码的头部，这就叫做变量提升。
## 三、标识符的规则

   标识符有一套命名规则，不符合规则的就是非法标识符。JavaScript 引擎遇到非法标识符，就会报错。
   * 第一个字符，可以是任意 Unicode 字母（包括英文字母和其他语言的字母），以及美元符号（$）和下划线（_）。
   * 第二个字符及后面的字符，除了 Unicode 字母、美元符号和下划线，还可以用数字0-9。
  * 例如
   ``` javascript
   arg0
   _tmp
   $elem
   π 
```
其次：中文是也是合法的标识符，也可以用作变量名。
* 注意

JavaScript 有一些保留字，不能用作标识符：
```
arguments、break、case、catch、class、const、continue、debugger、default、delete、do、else、enum、eval、export、extends、false、finally、for、function、if、implements、import、in、instanceof、interface、let、new、null、package、private、protected、public、return、static、super、switch、this、throw、true、try、typeof、var、void、while、with、yield
```
## 四、if else语句

* 语法
  
  if(表达式){语句1}
  else{语句2}

  {}在语句只有一句的时候可以省略，但是一般不建议这么做。
*  结构
  
```javascript
if (m === 3) {
  // 满足条件时，执行的语句
} else {
  // 不满足条件时，执行的语句
}
```
* 对同一个变量进行多次判断时，多个if...else语句可以连写在一起。
  
   比较好用的一种写法
   ```javascript
   if (表达式){
       语句
   }
   else if(表达式){
       语句
   } else {
       语句
   }
## 五、while for语句

1. while语句
``` javascript
switch (fruit) {
  case "banana":
    // ...
    break;
  case "apple":
    // ...
    break;
  default:
    // ...
}
```
* 注意

上面代码根据变量fruit的值，选择执行相应的case。如果所有case都不符合，则执行最后的default部分。需要注意的是，每个case代码块内部的break语句不能少，否则会接下去执行下一个case代码块，而不是跳出switch结构。

2. while循环语句

While语句包括一个循环条件和一段代码块，只要条件为真，就不断循环执行代码块。
```javascript
while (条件)
  语句;

// 或者
while (条件) 语句;
```

3. for语句

for语句是循环命令的另一种形式，可以指定循环的起点、终点和终止条件。它的格式如下。
```javascript
for (初始化表达式; 条件; 递增表达式)
  语句

// 或者

for (初始化表达式; 条件; 递增表达式) {
  语句
}
```
for语句后面的括号里面，有三个表达式。
* 初始化表达式（initialize）：确定循环变量的初始值，只在循环开始时执行一次。
* 条件表达式（test）：每轮循环开始时，都要执行这个条件表达式，只有值为真，才继续进行循环。
* 条件表达式（test）：每轮循环开始时，都要执行这个条件表达式，只有值为真，才继续进行循环。

## 六、break continue

* break语句和continue语句都具有跳转作用，可以让代码不按既有的顺序执行。


1. break语句用于跳转代码块或循环。
```javascript
var i = 0;

while(i < 100) {
    console.log('i 当前为:' + i );
    i++;
    if(i === 10) break;
}
```
上面代码只会执行10次循环，一旦i等于10，就会跳出循环。

* continue语句用于立即终止本轮循环，返回循环结构的头部，开始下一轮循环。

```javascript
var i = 0;
while (i < 100){
  i++;
  if (i % 2 === 0) continue;
  console.log('i 当前为：' + i);
}
```
上面代码只有在i为奇数时，才会输出i的值。如果i为偶数，则直接进入下一轮循环。
## 七、label
* 语法
```javascript
foo: {
    console.log(1);
    break foo;
    console.log('本行不会输出');
    }
    console.log(2);
```
下面代码中foo就是个label,1则是语句。
```javascript
{
    foo: 1
}
```







