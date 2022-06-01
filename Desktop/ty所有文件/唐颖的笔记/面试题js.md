##### var、let、const

- var命令

  - 全局作用域var变量会挂载到window对象上，而let、const不会

- let命令

  - let、const有块级作用域

    - 块级作用域就是变量只在大括号{}内有效。

  - 在for循环中，如果使用let声明变量，那么每一次输出的值都不一样。

    ![image-20220322141225521](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220322141225521.png)

  - let、const不存在变量提升，
  
    - 它们声明的变量一定要声明后使用，否则报错。
  
  - let、const有暂时性死区
  
    - 暂时性死区：在代码块内，使用let命令声明变量之前，该变量都是不可用的。ES6明确规定，如果区块中存在let和const命令，这个区块对这些命令声明饿变量一开始就形成了封闭区域。凡是在声明变量前使用，就会报错。

- 区别
  - 全局作用域var变量会挂载到window对象上，而let、const不会
  - var变量名可以重复，而let、const不能
  - const变量不可以修改，而let、const可以
    - 但是如果const声明的是引用类型，这时候是可以修改它的属性，比如对象、数组，所以我们常用const声明常量。

##### 实例方法、静态方法、原型方法

- 实例方法
  - 构造函数中this上添加的成员，只有实例才能访问，无法直接调用

- 静态方法
  - 构造函数本身上添加的成员

- 原型方法
  - 原型中的方法，实例和构造函数都可以访问

##### call（）、apply（）、bind（）

- 这三个方法都是重定向this这个对象的。bind返回的是一个新的函数，必须调用才会执行，所以bind方法后需要加（）。

- 传参比较
  - ![image-20220415142427625](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220415142427625.png)

##### for-in、for-of

- 两者都是严格的迭代语句
- for-in
  - 用于枚举对象中的非符号属性。
  - ECMAScript中的对象是无序的 ，因此for-in语句不能保证返回对象属性的顺序。即所有可枚举的属性都会返回一次，但返回顺序因浏览器而异。
  - 若迭代的变量是null或undefined，则不执行循环体。

- for-of
  - 用于遍历可迭代对象的元素。ES6增加的语句，循环遍历一组由一个迭代器（iterator）产生的值。
  - 在for（XYZ of ABC）中，XYZ既可以是一个赋值表达式也可以是一个声明。
  - 在一个函数中，使用break，continue，return，以及抛出异常，循环可以提前被终止。
  - 该语句会按照可迭代对象的next（）方法产生值的顺序迭代元素。
  - 它循环便利店的值必须是一个可迭代对象（iterable）。

- 两者的区别
  - for-in遍历数组中的索引/键/下标，for-of遍历数组中的元素value。
  - for-of不能遍历对象，它没有迭代器对象。遍历对象的属性使用for-in。

##### 迭代方法

- 有五种：every（）、some（）、map（）、filter（）、forEach（）

##### map（）、filter（）方法

- 两种方法都接受两个参数
- map
  - 适合从数组中筛选满足要求的元素

- filter
  - 适合创建一个与原始数组元素对应的新数组

##### typeof、instanceof、toString

- typeof
  - 用于判断一个表达式、对象或原始值，返回一个字符串

- instanceof
  - 该运算符用来判断一个构造函数的prototype属性所指向的对象是否存在另外一个要检测对象的原型链上，返回boolean值。
  - 语法：obj instanceof Object； 实例obj在不在Object构造函数中
  - 只能用来判断对象和函数，不能用来判断字符串和数值。

- toString
  - toString.call(obj)来检测对象类型

- constructor属性
  - 实例对象的原型中有一个属性constructor指向实例的构造函数，它返回一个指向创建了该对象原型的函数引用。

##### new一个对象发生了什么

- 在JavaScript中我们经常需要写一个构造函数来新建对象，比如下面这样：

  ```
  function foo(){
  this.name='唐颖';
  this.age=18;
  }
  const foo=new foo();
  ```

- 那么在new一个对象的过程中它具体发生了什么？主要有以下这几步：
  1. 创建一个全新的对象
  2. 把这个新对象的 _ proto _ 属性指向构造函数的prototype
  3. 把这个新对象绑定到构造函数调用时的this
  4. 如果函数没有返回其他对象，那么new操作就自动返回这个新对象

- 这里面涉及到了原型链的挂载，this的绑定。


##### JavaScript八股|==和===的区别

- ==
  - 宽松等于

- ===
  - 严格等于

##### 箭头函数的使用和this的指向

- 定义函数的方式
  - function
  - 对象字面量
  - ES6中的箭头函数 

- 箭头函数中this的使用
  - 问题：箭头函数中的this时如何查找的？
  - 答案：向外层作用域中，一层层查找this，直到有this的定义。

##### v-if和v-for可以一起使用吗？

- 不推荐v-if和v-for一起使用
  - 当v-for和v-if一起使用时，v-for具有比v-if更高的优先级。

##### null和undefined的区别 

- 















































