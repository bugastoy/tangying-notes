Vue的生命周期

- Lifecycle
  - 在vue实例或组件中定义了一些函数，在某个时刻就会回调这些函数。当然，如果我们没有实现这个函数，该函数不会被调用。

- beforeCreate（）

  - 创建实例之前执行的钩子事件
  
- created（）

  - 创建组件完成时回调
  
- beforeMount（）

  - 将编译完成的HTML挂载到对应虚拟dom时触发的钩子
  - 此时页面并没有内容
  
- mounted（）

  - 组件挂载到DOM时回调
  
- beforeUpdate（）

  - 更新之前的钩子
  
- updated（）

  - 当界面发生刷新的时候回调
  
- beforeDestory（）

  - 实例销毁之前执行的钩子
  
- destoryed（）

  - 实例销毁完成执行的钩子
  - 组件被销毁
  
- 实例的创建和销毁的一个机制

  ![image-20220404202004914](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220404202004914.png)

##### Vue中的MVVM

##### 基本语法

- Mustache语法
  - 双大括号语法中，不仅可以直接写变量，也可以写简单的表达式。

- v-once
  - 该指令表示元素和组件只渲染一次，后面不需要跟任何表达式，不会随着数据的改变而改变。

-   v-html
  - 将代码按照HTML格式进行解析，并显示对应内容

- v-pre
  - 用于显示原本的Mustache语法

- v-text
  - 用于将数据显示在页面中，通常接受一个string类型

- v-cloak
  - 在解析之前，div有一个属性v-cloak
  - 在vue解析之后，div没有一个属性v-cloak

- v-bind
  - 用于动态绑定一个或多个属性值，或者向另一个组件传递props值
  
  - 语法糖
  
    ![image-20220407101833726](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220407101833726.png)

- v-bind动态绑定class（对象语法）

  - 绑定方式：对象语法、数组语法
    - 对象语法的含义是：class后面跟的是一个对象
    - 数组语法：class后面跟一个数组
  - 对象语法有以下用法：
    - 用法一：直接通过{}绑定一个类
    - 用法二：通过判断，传入多个值
    - 用法三：和普通的类同时存在，并不冲突
    - 用法四：如果过于复杂，可以放在一个methods或computed中

- v-bind绑定style
  - 用来绑定一些CSS内联样式 

##### 计算属性

- 计算属性是写在实例的computed选项中的，使用“大胡子语法”调用。  


- 计算属性setter和getter
  - 每一个计算属性都包含一个getter和setter，可以用getter读取属性，也可以提供一个setter方法。

##### ES6补充

-  for循环使用var定义的变量在执行前被系统不断回调，因此每次产生的i值都一样，因为for循环内不存在块级作用域，在ES6之前，可以使用闭包解决这个问题，因为函数是一个作用域。在ES6中我们使用let来定义这个变量i，使for循环内存在块级作用域。在JS里面，只有函数functi有自己的作用域。

- 没有块级作用域时引起的的问题：for循环
  - 情况一：直接使用var声明，ES5中不使用闭包
  - 情况二：ES5中使用闭包
  - ES6中的let

- const
  - 在JS中，一旦给const修饰的标识符被赋值之后，不能修改。
  - 在使用const定义标识符，必须进行赋值。
  - 常量的含义是指向的对象不能修改，但是可以改变对象内部的属性。
  - 在ES6开发中，优先使用const，只有在需要改变某一个标识符时才使用let。

- 对象字面量的增强写法

  - 属性的增强写法

    ![image-20220421142101232](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220421142101232.png)

  - 函数的增强写法

    ![image-20220421142049737](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220421142049737.png)

##### v-on事件监听

- v-on指令
  - 作用：绑定事件监听器
  - 缩写：@
  - 预期：Function|Inline Statement|Object
  - 参数：event

- v-on的参数传递问题
  1. @click事件监听或者监听的方法不需要额外参数的时候，方法后的（）可以省略。但是如果方法本身中有一个参数，就会默认将原生事件event参数传递进去。
  2.  方法定义时，需要event对象，同时又需要其他参数，我们可以手动的获取到浏览器参数的event对象：$event

##### v-on修饰符

- .stop修饰符

  - 作用：阻止事件冒泡
  - 调用event/stopPropagation()

  ![image-20220421162119068](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220421162119068.png)

- .prevent

  - 阻止默认事件

  - 调用event.preventDefault()

    ![image-20220421162600649](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220421162600649.png)

- .(KeyCode|keyAlias)

  - 监听某个键，特定键被按下时才会被触发

    ![image-20220421162939026](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220421162939026.png)

- .once
  - 只触发一次回调（只有当第一次点击有反应）

##### v-if、v-else-if、v-else的使用

##### 登陆切换的案例

- 补充html知识

  - label for 点击文字区域的瞬间，光标聚焦在搜索框

  ![image-20220421195142049](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220421195142049.png)

- input复用问题
  - 问题描述：在有输入内容的情况下，切换了类型，发现文字依然显示之前输入的内容？
  - 解答：Vue在进行DOM渲染时，出于性能考虑，会尽可能地复用已经存在的元素，而不是重新创建新的元素。

##### v-show

- v-show和v-if的用法类似，用于决定一个元素是否渲染
- 开发中如何选择？
  - 当需要在显示与隐藏之间切换很频繁时，使用v-show
  - 只有一次切换时，使用v-if
- v-show、v-if的区别
  - v-show：当条件为false时，它只是给元素添加一个行内样式：display：none。
  - v-if：当条件为false时，包含v-if指令的元素，直接消失在dom中。

##### v-for以及为什么要给组件绑定key值

- v-for遍历对象
  1. 在遍历对象的过程中，如果只是获取到一个值，那么获取到的是value
  2. 获取key和value，格式：（value,key)

- 组件的key属性

  - 官方推荐在使用v-for时，给对应元素或组件添加上一个key属性。

    ![image-20220421205125403](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220421205125403.png)

  - 实质上，我们是用key给每一个节点做唯一标识。作用是为了高校的更新虚拟DOM。

  - 数组渲染之后，在中间插入元素的过程

    ![image-20220421204508390](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220421204508390.png)

##### v-if和v-for可以一起使用吗？

- 官方文档不推荐v-if和v-for一起使用
  - 当v-for和v-if一起使用时，v-for具有比v-if更高的优先级。

##### 数组中的响应式方法

1. push（）：在数组最后添加元素
2. pop（）：删除数组中的最后一个元素
3. shift（）：删除数组中的第一个元素
4. unshift（）：在数组前面添加元素
5. splice（）：删除元素、插入元素、替换元素
   - 删除元素：第二个参数传入你要删除几个元素（如果没有传，就删除后面所有的元素）
   - 替换元素：第二个参数表示要替换的元素个数，后面是用于替换的元素
   - 插入元素：第二个参数传入0，后面跟上要插入的元素
6. sort（）
7. reverse（）

- 注意，这种方式不是响应式的：通过索引值修改数组中的元素


- 修改数组中的元素还可以用以下方法：

  ![image-20220421212820797](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220421212820797.png)

##### 购物车案列遇到的一些问题

1. toFixed（）括号里是给数字取的小数位
2. 过滤器filters，个人觉得类似于封装函数有一个返回值，可以进行调用。Vue3已经移除过滤器。

##### JavaScript高阶函数补充（filter/map/reduce)

- 运用高阶函数的函数式编程 

- **filter**

  - filter中的回调函数有一个要求：必须返回一个布尔值

  - true：当返回true时，函数内部会自动将这次回调的n加入到新的数组中

  - false：当返回false时，函数内部会过滤掉这次的n

    ![image-20220422162846665](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220422162846665.png)

- **map**

  - 可以对数值进行操作，自带遍历

    ![image-20220422163512746](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220422163512746.png)

- **reduce**

  - 作用：对数组中所有的内容进行汇总

  - 适用场景：求数组和的时候

  - reduce必须传两个参数，其中一个是它的回调函数，一个是默认值。在回调函数里，也有两个参数，第一个参数是preValue—上次的返回值，在第一次回调输出的时候preValue是我们的默认值，回调函数中的第二个参数就是遍历数组的值。

    ![image-20220422164223816](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220422164223816.png)

- 求数组中小于100的数，再乘以2，再求它的总和

  ![image-20220422164858101](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220422164858101.png)

![image-20220422165242371](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220422165242371.png)

#####  v-model

- v-model的使用和原理
  - Vue中使用v-model指令来实现表单元素和数据的双向绑定
  - 原理：v-model其实是一个语法糖，本质上是包含两个操作
    1. v-bind绑定一个value属性
    2. v-on指令给当前元素绑定input事件

- v-model结合radio类型使用
  - 用到的知识点：
    - label标签，在label元素内点击文本，就会触发控件，通常一个label绑定一个input
    - 设置同一个name属性，可以使按钮在同一时间只选择一个

- v-model结合checkbox类型使用
  - 单选框
    - v-model即为布尔值
    - 此时的value不影响v-model的值
  - 多选框
    - 对应的data中的属性是数组
    - 当选中某一个时，就会将input中的value添加到数组中

- v-model结合select类型使用

  - select元素可创建单选或多选菜单，它的option标签用于定义列表中的可选选项。

    ![image-20220422211657147](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220422211657147.png)

  - 单选

    - v-model绑定的是一个值

  - 多选（multiple）

    - v-model绑定的是一个数组

      ![image-20220422211758363](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220422211758363.png)

  ##### v-model修饰符的使用

  ![image-20220423193422648](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220423193422648.png)

  - lazy修饰符
    - v-model默认在input事件中同步输入框的数据的。
    - lazy修饰符可以让数据在失去焦点或者回车时才会更新。
  - number修饰符
    - 默认情况下，在输入框中无论输入的是字母还是数字，都会被当作字符串类型进行处理。
    - 当我们处理的是数字类型时，最好直接将内容当作数字类型处理。
    - number修饰符可以让在输入框中输入的内容自动转成数字类型。
  - trim修饰符
    - 当输入的内容首尾有很多空格，需要将其去除的情况。
    - trim修饰符可以过滤内容左右两边的空格。

##### 组件化的基本使用

![image-20220423194957547](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220423194957547.png)

- 组件的使用分成三个步骤

  ![image-20220423201354251](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220423201354251.png)<img src="C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220423204817117.png" alt="image-20220423204817117" style="zoom: 67%;" />

  - 创建组件构造器

    - Vue.extend（）：
      - 调用Vue.extend（）创建的是一个组件构造器

  - 注册组件

    - 全局组件，意味着可以在多个Vue实例下面使用

    - 局部组件，只在一个Vue实例里面定义

      ![image-20220423211547087](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220423211547087.png)

  - 使用组件

    - 组件必须挂载在某个Vue实例下，否则它不会生效。

##### 父组件和子组件的区分

![image-20220425135558699](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425135558699.png)

##### 注册组件的语法糖写法

- 注册的语法糖写法主要省去了调用Vue.extend（）的步骤，而是可以直接使用一个对象来代替。

- 语法糖注册全局组件和局部组件：

  <img src="C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425160755189.png" alt="image-20220425160755189" style="zoom:50%;" />

  <img src="C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425160744122.png" alt="image-20220425160744122" style="zoom: 50%;" />

##### 组件模板抽离的写法

1. 使用<script>标签

   ![image-20220425162749438](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425162749438.png)

2. 使用<template>标签

   ![image-20220425162729070](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425162729070.png)

#####  组件的data对象为什么要用一个函数返回

- 组件内部不能访问父组件或Vue实例的数据

- 组件数据的存放

  - 组件对象可以用data属性，method属性等等

  - 但是这个属性必须是函数

  - 而且这个函数返回一个对象，对象内部保存着数据

    ![image-20220425165140114](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425165140114.png)

- 组件中的data为什么必须是函数

  - 函数每次调用都会返回一个新的对象，每次返回的对象都会保存各自的地址值，这样组件之间修改数据的时候就不会互相影响。

##### 父子组件通信—父传子

- 产生

  - 在开发中，往往一些数据需要从上层传到下层
    - 比如在一个页面中，我们从服务器请求到了很多数据。
    - 其中一部分数据，并非是我们整个页面的大组件来展示的，而是需要下面的子组件进行展示。
    - 这时候，并不会让子组件再次发送一个网络请求，而是直接让大组件（父组件）将数据传递给小组件（子组件）。

- 如何进行父子组件间的通信？Vue官方提到

  - 通过props向子组件传递数据
  - 通过事件向父组件发送消息

- 真实开发中，Vue实例和子组件的通信和父组件和子组件的通信过程是一样的。

  ![image-20220425185328176](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425185328176.png)

- props基本语法
  - 方式一：字符串数组，数组中的字符串就是传递时的名称。
  - 方式二：对象，对象可以设置传递时的类型，也可以设置默认值等。

- 一个简单的props传递

- 数组方式

  ![image-20220425195743485](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425195743485.png)

![image-20220425195821095](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425195821095.png)

- 对象方式（常用）

  ![image-20220425201911071](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425201911071.png)

- 验证支持的数据类型

  - String

  - Number

  - Boolean

  - Array

  - Object

  - Date

  - Function

  - Symbol

  - 自定义类型

    ![image-20220425201848686](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425201848686.png)

##### 父子组件通信—props驼峰标识

- props如果使用的是驼峰命名，Vue实例中应该使用下面方式传递

![image-20220425202942592](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425202942592.png)

##### 父子组件通信—子传父

- 子组件传递事件或数据到父组件中使用的方式：自定义事件

- v-on不仅可以监听事件，还可以用于组件间的自定义事件

- 自定义事件的流程

  - 在子组件中，通过$emit（）来发射事件

    ![image-20220425212126794](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425212126794.png)

  - 在父组件中，通过v-on来监听子组件事件

    ![image-20220425212248765](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425212248765.png)

    ![image-20220425212240736](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220425212240736.png)

##### 项目演示

- npm install
- npm run serve

#####  结合双向绑定案例

![image-20220427143900313](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220427143900313.png)

##### 父子组件的访问方式—父访问子

1. $children

   - this.$children是一个数组类型，它包含所有子组件对象，我们可以通过遍历取出想要的数据。

2. $refs

   - $refs是一个对象类型，默认是一个空对象，给子组件添加一个key值，根据这个key值才能访问到这个组件

     ![image-20220428151906394](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220428151906394.png)

     ![image-20220428151922934](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220428151922934.png)

##### slot—插槽的基本使用

- 插槽分为
  
  - 具名插槽
  - 匿名插槽
  
- 插槽的基本使用
  
  - 组件的插槽可以让我们封装的组件更具有扩展性。
  
- 具名插槽的基本使用

  ![image-20220428160325666](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220428160325666.png)

#####  前端模块化

- 常见的模块化规范：
  - CommonJS、AMD、CMD、ES6的Modules

##### ES6模块化的导入和导出

-  导出方式

  ![image-20220428195558762](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220428195558762.png)

- 导入

  ![image-20220428195616554](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220428195616554.png)

- export default
  - 某些情况下，一个模块中包含某个功能，我们并不希望给这个功能命名，让导入者可以自己命名，此时可以使用export fault。
  - 在同一个模块中，不允许存在多个export fault。 

- import使用

  - import命令用来加载对应的模块

  - 需要在HTML代码中引入js文件，并且类型设置为module

    ![image-20220428200438749](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220428200438749.png)

  - 使用*统一全部导入

    ![image-20220428200702005](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220428200702005.png)

##### webpack的介绍和安装

![image-20220428201512894](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220428201512894.png)

#####  webpack中使用css文件的配置

- webpack
  - webpack可以处理我们写的js代码，它还会自动处理js之间相关的依赖。
- loader
  - 在开发中，当我们需要加载css、图片，将.vue文件转成js文件等等时候，我们可以给webpack拓展对应的loader来解决，不同的文件处理会用到不同的loader。

##### 创建Vue时el和template的关系

- vue内部源码会把图一中的div换到图二的div里面

  ![image-20220503194725490](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220503194725490.png)

  ![image-20220503194759572](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220503194759572.png)

##### 横幅plugin的使用	

![image-20220504141933777](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220504141933777.png)

##### HtmlWebpackPlugin的使用

![image-20220504142555106](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220504142555106.png)

##### webapck-dev-server搭建本地服务器

- 在开发阶段便于测试我们的代码

![image-20220506192219504](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220506192219504.png)

##### webpack配置文件的分离（未做）

- 有一节老师打包压缩丑化文件时没有做，所以这一节也略过。

![image-20220507144305736](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220507144305736.png)

![image-20220507144309841](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220507144309841.png)

##### vuecli脚手架的介绍和安装配置

- CLI的概念
  - CLI是Command-Line Interface，翻译为命令行界面，但是俗称脚手架。
  - 使用vue-cli可以快速搭建Vue开发环境以及对应的webpack配置。

- CLI的安装
  - npm install -g @vue/cli@4.5.12
  - 我安装的脚手架版本是4.5.12，老师安装的是3.2.1。
  - 搜索博客，发现3和4其实区别较小，所以我目前选择直接安装4。

-  npm在电脑中的地址
  - C:\Users\86189\AppData\Roaming\npm

- CLI2中关闭Eslint规范的方式

  - 在config/index.js中useEslint设置为false，重新运行就即可关闭。

    ![image-20220507201311903](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220507201311903.png)

##### runtime-complier和runtime-only的区别

- Vue程序运行过程

  ![image-20220507202126368](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220507202126368.png)

-  区别
  - runtime-compiler
    - template—ast—render—vdom—UI
  - runtime-only（性能更高，代码量更少）  
    - render-vdom-UI

- 简单总结
  - 在开发中，依然使用template，就需要选择Runtime-Complier
  - 如果选择使用.vue文件夹开发，那么可以选择Runtime-only
  
- creatElement函数的用法
  1. 普通用法
     - createElement（‘标签’，{标签的属性}，[' '])
  2. 传入组件对象
     - return createElement(App)
     - 上面的代码，表示可以直接传过来一个App对象，在这里进行创建另一个App对象

- render函数的写法

  - 用于渲染页面

  - ```
    render:function(h){  //h是createElement函数
    	return h(App)
    }
    ```

- 问题：vue文件中的template是谁处理的？
  - 是由vue-template-complier解析，并且这个是开发时依赖。所有的vue组件内都不包含template，它包含的都是render函数。

##### VueCLI3创建项目结构

- npm run build 

  ![image-20220508144901180](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220508144901180.png)

- vue中的类型检测
  - vue2：flow-type，属于facebook
  - vue3：TypeScript，属于microsoft

- vue-cli3与2有很大区别
  - vue-cli3的设计原则是“0配置”，移除了配置文件根目录下的，build和config等目录。
  - 提供了vue ui命令，提供了可视化配置。
  - 移除了static文件夹，新增了public文件夹，并且index.html移到了public下。

- Vue CLI3初始化项目，创建项目
  - vue create 项目名称

- 英文词汇
  - preset配置
  - manually手动地
  - progressive先进的

##### VueCLI3配置的查看和修改

- vue的真实版本

  - node文件夹—vue—dist—vue.js中查看

  - vue文件夹—package.json中查看

    ![image-20220508151752768](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220508151752768.png)

    ![image-20220508151546219](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220508151546219.png)

    ![image-20220508151514001](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220508151514001.png)

- git
  - git commit -m  '修改配置文件'
  - git add
  - git update

##### 箭头函数的使用和this的指向

- 定义函数的方式
  - function
  - 对象字面量
  - ES6中的箭头函数 

- 箭头函数中this的使用
  - 问题：箭头函数中的this时如何查找的？
  - 答案：向外层作用域中，一层层查找this，直到有this的定义。

##### 什么是路由和其中的映射关系

- 路由
  - 通过互联网把信息从源地址传输到目的地址的活动。

##### 前端渲染后端渲染

- 后端路由
  - 早期的网站开发，服务器直接生产渲染好对应的HTML页面，返回给客户端进行展示。
  - 一个网站，多个页面服务器如何处理？
    - 一个页面有自己对应的网址，也就是URL。
    - URL会发送到服务器，服务器会通过正则对该URL进行匹配，并且最后交给Controller进行处理。
    - Controller进行各种处理，最终生成HTML或者数据，返回给前端。

-  前端渲染
  - 浏览器中显示的网页中的大部分内容，都是由前端写的js代码在浏览器中执行，最终渲染出来的网页。

- 网页发展
  - 前后端分离阶段
    - 后端提供API返回数据，前端通过Ajax获取数据，并且通过JavaScript将数据渲染到页面中。
  - 单页面富应用SPA阶段
    - 在前后端分离的基础上加了一层前端路由。

- 前端路由的核心
  - 改变URL，但是页面不进行整体的刷新。

##### URL的hash和HTML5的history

- URL的hash
  - 通过location.hash=' '来改变href，但是不发生刷新。

- HTML5的history模式

  - history.pushState({}, '   ' ,home')

    - 改变url，不刷新

    - 类似于栈结构

  - history.back（）

    - 返回上一个页面

  - history.replaceState({}, '   ' ,home')

    - 替换前一个页面，无返回按钮

  - history.go（）

    - 括号内的数字，正数表示添加一个页面，负数表示返回之前的页面
    - history.go(-1)等于history.back()

    - history.go(1)等于history.forward()

##### vue-router的安装和配置

1. 通过Vue.use(插件)，安装插件

2. 创建VueRouter对象

   ![image-20220514202226946](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514202226946.png)

3. 配置路由和组件之间的映射关系

   ![image-20220514202250534](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514202250534.png)

4. 将router对象传入到Vue实例

   ![image-20220514202308069](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514202308069.png)

5. 最后导出，在Vue实例中进行挂载 

   ![image-20220514202332191](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514202332191.png)

##### 路由映射配置和呈现

- 使用路由的步骤
  1. 创建路由组件
  2. 配置路由映射：组件和映射关系
  3. 使用路由：通过< router-link >和< router-view >

- router-link
  - 用于显示组件
  - vue-router注册过的组件，是全局组件
  - 它会被渲染成一个a标签

- router-view
  - 根据不同的路径，设置组件在什么时候、哪个位置出现
  - 相当于占位，组件会替代它的位置出现

- HTML5的history模式

  ![image-20220513141231088](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220513141231088.png)

##### router-link的属性

- tag属性
  - 可以指定router-link之后渲染成什么组件

- replace属性
  - 后退键返回不能返回到上一个页面中。

- active-class属性

  - 在按钮活跃状态时，会添加active-class这个类

  - 当router-view对应的路由匹配成功时，会自动给当前元素设置一个router-link-active的class设置active-class可以修改默认的名字。

    ![image-20220513142609599](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220513142609599.png)

  - 改属性也可以通过router实例修改

    ![image-20220513142639620](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220513142639620.png)

##### 通过代码跳转路由

![image-20220513144346837](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220513144346837.png)

![image-20220513144212955](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220513144212955.png)

- 跳转路由的方法，考过

  - this.$router.push()

    - 跳转有记录

    - $router其实是我们创建的router里面的对象

  - this.$router.replace()

    - 替换当前页面

  - this.$router.go()

##### 动态路由的使用

- this.$route表示当前哪个路由处于活跃状态，就取哪个路由

- 使用下面的代码，可以跳转到相应路由，拿到传过来的数据

  ![image-20220514104354671](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514104354671.png)

- 使用v-bind让属性动态绑定data数据

- 词汇

  - parameters参数

##### 打包文件的解析

- 这节老师讲的是CLI3打包文件，当我们npm run build打包文件时，会默认打包成以下三个文件

  - app

    - 开发生产的业务代码

  - mainfest

    - webpack内部有一个类似于_ webpack_require_的函数它的作用就是对我们打包的几个模块化的代码做底层支撑，它会将底层支撑的代码放入mainfest

      ![image-20220514111719490](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514111719490.png) 

  - vendor

    - 第三方提供的，比如vue

![image-20220514112149940](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514112149940.png)

##### 路由懒加载的使用

- 懒加载
  - 官方解释，当打包构建应用时，JavaScript包会变得非常大，会影响页面加载。
  - 如果能把不同路由对应的组件分割成不同的代码块，当路由被访问的时候才加载对应组件，这样就更高效。
  - 用到的时候，再加载

- 路由懒加载的作用
  - 将路由对应的组件打包成一个个js代码块
  - 只有在这个路由被访问到的时候，才加载对应的组件

- 路由懒加载的方式

  ![image-20220514143833636](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514143833636.png)

##### 路由的嵌套使用

- 路径和组件的关系

  - 实现嵌套路由有两个步骤
    - 创建对应的子组件，并且在路由映射中配置对应的子路由
    - 在组件内部使用router-view标签

  - 嵌套路由也可以配置默认的路径，配置方式如下：

  ![image-20220514195003010](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514195003010.png)

##### vue-router—参数传递

- 传递参数主要有两种方式

- params类型

  - 配置路由格式：/router/id

  - 传递的形式：在path后面跟上对应的值

    ![image-20220514200533033](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514200533033.png)

    ![image-20220514200551399](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514200551399.png)

  - 传递后形成的路径：/router/zhangsan

    ![image-20220514200416178](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514200416178.png)

- query类型

  - 需要传递大量数据时优先使用此方式，因为它传的是一个对象

  - 配置路由格式：/router

  - 传递的方式：对象中使用query的key作为传递方式

  - 传递后形成的路径，（query{ },后面加逗号）

    ![image-20220514210159956](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514210159956.png)

- 当绑定的是按钮，如何传递参数

  - 方式其实是类似的

  - 给按钮绑定一个响应函数

    ![image-20220514212100543](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514212100543.png)

  - 使用this.$router.push传递参数

  - push方法里面传入对象用来保存我们的数据，query里面也是传入一个对象用来保存数据

    ![image-20220514212122995](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220514212122995.png)

##### vue-router之router的由来

- 重要结论

  - 所有的组件都继承自Vue类的原型（方法、属性）

  - 例如：

    - 在vue的原型上添加一个方法

      ![image-20220516100907021](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220516100907021.png)

      ![image-20220516100926844](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220516100926844.png)

    - 即所有组件都能使用这个方法

- vue-router的源码

  - 下面两个代码实现的是同一个功能，往object里面加属性

  ![image-20220516101634542](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220516101634542.png)

- $route和$router是有区别的

  - $router为VueRouter实例，想要导航到不同的URL，则使用$router.push方法

  - $route为当前router跳转对象里面可以获取name、path等

    ![image-20220516102036998](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220516102036998.png)

##### vue-router全局导航守卫使用

- 利用beforeEach

  - 首先，在钩子定义中使用meta定义一些标题

  - meta：元数据（描述数据的数据）

    ![image-20220516111344899](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220516111344899.png)

  - 其次，利用导航守卫，修改我们的标题

    ![image-20220516111355520](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220516111355520.png)

- 导航钩子的三个参数解析

  - to，即将进入的目标的路由对象
  - from，当前导航即将要离开的路由对象
  - next，调用该方法后，才能进入下一个钩子

- 后置钩子，afterEach，不需要主动调用next（）函数
- 上面我们使用的导航守卫，被称为全局守卫
  - 路由独享守卫
  - 组件内守卫

##### keep-alive

- keep-alive是Vue内置的一个组件，可以使被包含的组件保留状态，或避免被重新渲染。

- 记录离开时路由的状态

  - 使用组件内守卫

  - activated（）

    - 路由活跃时回调的方法

  - deactivated（）

    - 这两个函数只有在使用keep-alive时才能使用

      ![image-20220516152738518](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220516152738518.png)

  - beforeRouterLeave（）

    ![image-20220516152139243](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220516152139243.png)

- 过程出现一个报错

  - 在router文件夹下的index.js中加入如下代码，错误消失

    ![image-20220516152250873](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220516152250873.png)

##### keep-alive的属性

- exclude属性

  - 把name传到exclude中，该组件不会被缓存

  ![image-20220516153410043](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220516153410043.png)

- include属性

  - 把name传到include中，该组件会被缓存

##### tabbar—基本项目的构建步骤

- 引用css样式文件

  - 可以在main.js中使用require引用

    ![image-20220516162049436](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220516162049436.png)

  - 也可以在App组件的style中用以下方式引用，使用@

    ![image-20220516162148890](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220516162148890.png)

- 让四个div水平底部分布

- flex布局平分TabBar

- 自定义TabBarItem，可以传入图片和文字

  - 定义TabBarItem，并且定义两个插槽：图片、文字
  - 给两个插槽外层包装div，用于设置样式
  - 填充插槽
  
- 图片下面默认会跟div隔3个像素

  - 使用vertical-align:middle去除这部分空间

##### tabbarItem和路由结合效果

- 项目开发时组件存放方式

  ![image-20220520110739417](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220520110739417.png)

- 组件通信—父传子

  - 在App.vue中的组件定义path属性

    ![image-20220520113806979](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220520113806979.png)

  - 在子组件中使用props接受数据，这里设定接收到的是String类型的数据

    ![image-20220520113747335](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220520113747335.png)

- 修改模式为history

  ![image-20220520142407389](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220520142407389.png)

- 如何使点击的组件不同颜色

  - 获取到活跃的组件

  - 设置一个计算属性，用来判断组件是否显示颜色

    ![image-20220520144005376](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220520144005376.png)

- 动态绑定style样式

  - style绑定的语句太长了，所以我们使用一个计算属性

    ![image-20220520145714473](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220520145714473.png)

    ![image-20220520145811405](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220520145811405.png)

    上面的语句使用的是三元表达式，isActive判断组件是否活跃？活跃的话返回activeColor属性，否则为空

    ![image-20220520145643019](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220520145643019.png)

##### 文件路径的引用问题—起别名

-  src的别名

  ![image-20220520153141322](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220520153141322.png)

- html、dom中寻找路径使用波浪线~

  ![image-20220520153341075](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220520153341075.png)

##### Promise的基本使用

- promise的介绍
  - promise是异步编程中的一种解决方案

- 什么时候会处理异步事件？

  - 一种常见场景就是网络请求了。

  - 封装一个网络请求的函数，因为不能立即拿到结果，所以不能直接返回。

  - 往往会传入一个函数，在数据请求成功时，将数据通过传入的函数回调出去。

  - 当网络请求变得很复杂时，会变成回调地狱。

    ![image-20220520155019160](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220520155019160.png)

- 链式编程

- 什么情况下会用到Promise？
  - 一般情况下是有异步操作时，使用Promise对这个异步操作进行封装。

- new Promise（）的执行过程

  ![image-20220524153451392](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220524153451392.png)

  - 当有异步操作的时候，放到Promise里面，当网络请求成功，异步操作拿到结果后，通过调用resolve把结果传到then函数里，在then函数里面进行代码处理

  - new=>构造函数（1.保存一些状态信息 2.执行传入的函数）

  - 在执行传入的回调函数时，会传入两个参数，resolve，reject，这两个参数本身又是函数

  - 在Promise里，网络请求成功会执行resolve函数，并且接着执行then函数；请求失败的时候，执行reject函数，并且不执行then函数，执行catch函数。参数都是传在resolve和reject函数的括号里。

    ![image-20220520200814730](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220520200814730.png)

- Promise的三种状态

  - pending：等待状态

  - fulfill：成功状态

  - reject：失败状态

  - async operation异步操作

    - wrapped into包裹进

    ![image-20220522135738288](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220522135738288.png)

- Promise的链式调用

  - reject作为参数是一个可选类型 reason？
  
    ![image-20220525155352373](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220525155352373.png)
  
  - 第一次的代码
  
    ![image-20220525155206286](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220525155206286.png)
  
  - 第二次的代码
  
    - 简写
  
    - 直接调用resolve进行回调传递res数据，不用new Promise
  
      ![image-20220525155852618](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220525155852618.png)
  
    
  
  - 第三次的代码
  
    - 最简洁
  
    - 省略resolve，直接回调传递的值
  
      ![image-20220525160321746](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220525160321746.png)
  
  - reject的两种捕获方式
  
    - 通过Promise.reject进行回调
  
    - 使用throw手动抛出异常
  
      ![image-20220525161028235](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220525161028235.png)

##### Promise的all方法

- all方法里传入一个数组，官方要求传入一个可迭代对象（可遍历的）

- 用法

  ![image-20220525163629054](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220525163629054.png)

##### Vuex概念和作用解析

- Vuex
  - 用来做状态管理的工具
  - 响应式
    - 数据发生改变界面跟着刷新

- 状态管理
  - 简单看成把需要多个组件共享的变量全部存储在一个对象里面
  - 将这个对象放在顶层的Vue实例中，让其他组件可以使用
  - 那么，多个组件就可以共享这个对象中的所有变量属性了

- 多个组件共享一个对象的原始方法

  - 声明一个对象

    ```
    const shareObj={
    	name:'ty'
    }
    ```

  - 在Vue的原型上添加这个对象

    ```
    Vue.prototype.shareObj=shareObj
    ```

    - 所有Vue组件都可以继承Vue的原型

  - 因此，组件中可以使用this加对象来访问对象中的属性了

    ```
    Vue.component({
    	this.shareObj.name
    })
    ```

  - 但是，这种方法无法做到响应式。Vuex插件就是为了这样一个在多个组件间共享状态的插件，用它就可以了。

- 什么状态需要再多个组件间共享？
  - 多个状态，在多个页面的共享问题
  - 比如用户的登录状态、用户名称、头像、地理位置
  - 比如商品的收藏、购物车的物品

##### Vuex—单页面到多页面状态管理切换

- 单页面的状态管理

  - State在View上显示，View上产生的Actions会改变State

  ![image-20220525210728358](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220525210728358.png)

  ![image-20220525210252959](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220525210252959.png)

- 安装开发时依赖--save和发布时依赖--save-dev

- 多页面状态管理

  - 当有异步操作时，要经过actions处理

  - 什么时候有异步操作呢？

    - 当我们发送网络请求的时候
    - 想后端请求一个API也是异步操作

  - backend后端frontend前端

  - 下面是官方的一幅图

    - Devtools是用来跟踪修改数据的一个工具

    ![image-20220526200547911](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220526200547911.png)

- 使用Vuex的简单方式
  - 提取出一个公共的store对象，用于保存在多个组件中共享的状态
  - 将store对象放置在new Vue对象中，这样可以保证在所有的组件中都可以使用到
  - 在其他组件中使用store对象中保存的状态即可
    - 通过this.$store.state来访问状态
    - 通过this.$store.commit('mutation中方法')来修改状态
  - 注意事项
    - 通过提交mutation的方式，而非直接改变store.state.count
    - 这是因为Vuex可以更明确的追踪状态的变化，所以不要直接改变store.state.count

##### Vuex—State单一树的概念

- Vuex几个核心概念
  - State用于保存状态
  - Getters类似于计算属性
  - Mutations
  - Action主要做一些异步操作
  - Module

- 单一状态树
  - single source of truth单一数据源
  - Vuex将所有需要管理的信息放在一个store里面
  - 所以在一个项目里面，永远只建立一个store

##### Vuex—getters详解

- 类似于全局的计算属性

- getters的使用

  - 筛选年龄的案例，在个别组件定义计算属性的方法

    - 在App中定义一个计算属性，使用filter函数过滤，下面代码表示：s是filter获取到的参数，也就是我们的students的数据，我们筛选的是年龄大于20的，所以回调s.age>20，返回的是true的时候会把元素返回

      ![image-20220527093045909](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527093045909.png)

    - 在App中渲染该属性

      ![image-20220527093304986](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527093304986.png)

  - 使用getters筛选年龄并且获取它的个数

    - getters里面定义的属性，可以有两个参数，一个是state，一个是getters，getters作参数可以方便我们二次调用已经定义的属性。

      ![image-20220527094509086](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527094509086.png)

    - 在组件中使用$store.getters.属性名渲染
    
      ![image-20220527094659762](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527094659762.png)
    
  - 案例：使用App组件设置年龄，把年龄传入getters中，过滤的年龄是从组件传来的
  
    - 之前在getters中，我们定义的都是属性
  
    - 需要从组件中传递参数到getters，可以想到函数传递参数的方式
  
    - 所以在getters中，我们可以定义一个函数
    
      ![image-20220527100038892](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527100038892.png)
    
    - 那么，在组件中我们就可以使用函数来进行渲染
    
      ![image-20220527100209788](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527100209788.png)
    
  - 计算平方的案例，使用到getters
  
    - 注意getters中定义的属性都有一个默认参数state
  
      ![image-20220527084843578](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527084843578.png)
  
      ![image-20220527084940009](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527084940009.png)

##### Vuex—mutations携带的参数

- Mutation状态更新

  - 官网明确说过，只要修改store中的state一定是通过mutation

  - Vuex的store状态的更新唯一方式：提交Mutation

  - Mutation包括两部分

    - 字符串的事件类型（type）
    - 一个回调函数（handler），该回调函数的第一个参数就是false

  - mutation的定义方式

    ![image-20220527102352868](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527102352868.png)

  - 通过mutation进行更新

    - 调用store的commit方法，传入的是事件类型

      ![image-20220527102427652](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527102427652.png)

- 案例

  - 实现加不同数

    ![image-20220527103352873](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527103352873.png)

  - 首先绑定一个方法

  - 添加的数不一样，那么我们使用传参的方式传入添加的数值

    ![image-20220527103529285](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527103529285.png)

  - 定义方法，使用commit方法把方法和count作为参数传到vuex中

    ![image-20220527103618364](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527103618364.png)

  - vuex中接受方法和参数

    ![image-20220527103744351](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527103744351.png)

- 案例：实现添加学生

  ![image-20220527104842307](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527104842307.png)

  - 绑定一个方法

    ![image-20220527104908008](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527104908008.png)

  - 方法和需要添加的对象作为参数传出

    ![image-20220527104952321](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527104952321.png)

  - 使用push方法 ，添加进student中

    ![image-20220527105105815](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527105105815.png)

- payload
  - 在通过mutation更新数据的时候，携带的一些新的参数，比如上面的stu，count

##### Vuex—mutations的提交风格

- commit

- type提交

  ![image-20220527131628732](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527131628732.png)

##### Vuex—数据的响应式原理

- 官方文档提过
  - 每个属性都有一个观察者模式Dep，监听数据的变化，Dep存放的是一个数组，
  - 里面放着很多个watcher，一个watcher对应一个组件，
  - 它会在组件渲染的过程中把“接触”过的数据 property 记录为依赖。
  - 之后当依赖项的 setter 触发时，会通知 watcher，从而使它关联的组件重新渲染。

- Vuex对应的响应式规则
  - 提前在store中初始化所需要的属性

- vue的一些响应式方法

  - Vue.set方法

    - 添加属性
    - 当我们调用这个方法时，vue内部会将我们添加的值添加到响应式系统中

    ![image-20220527141335327](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527141335327.png)

    ![image-20220527141554309](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527141554309.png)

  - Vue.delete方法

    - 删除属性
    - 同时在页面中删除

    ![image-20220527141914548](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220527141914548.png)

##### Vuex—mutations的类型常量

- 官方推荐以下写法

![image-20220528145518018](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528145518018.png)

![image-20220528145535753](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528145535753.png)

![image-20220528145558088](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528145558088.png)

![image-20220528145620856](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528145620856.png)

##### Vuex—actions的使用详解

- Mutation同步函数
  - 通常情况下，Vuex要求我们Mutation中的方法必须是同步方法
    - 主要原因是当我们使用devtools时，devtools可以帮我们捕捉mutation的快照。
    - 但是如果是异步操作，那么devtools将不能很好的追踪这个操作什么时候完成。

- 强调，不要再Mutation中进行异步操作
  - Action类似于Mutation，但是它可以代替Mutation进行异步操作。

- 强调，修改state中的状态必须是通过mutation

- Actions中的函数有一个默认参数context

  - context相当于store对象，是一个全局上下文

- 使用action进行异步操作

  - 组件中使用dispatch订阅异步操作的函数

    ![image-20220528152204690](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528152204690.png)

  - actions中使用commit提交异步操作

    ![image-20220528152115258](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528152115258.png)

    ![image-20220528152005220](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528152005220.png)

- dispatch方法可以传递两个参数

  - 一个是进行异步的函数，第二个参数是payload—携带的信息

    ![image-20220528153342270](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528153342270.png)

  - 异步操作的函数，可以回调传过来payload的函数

    ![image-20220528153541499](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528153541499.png)

    ![image-20220528153223240](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528153223240.png)

- Actions中的方法本身还可以返回一个Promise，那么上面代码还可以使用Promise优化

  ![image-20220528154759644](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528154759644.png)

##### Vuex—modules的使用详解

- Module
  - Vue使用单一状态树，那么也意味着很多状态都会交给Vuex来管理
  - 当应用变得复杂时，store对象就会变得很臃肿
  - 为了解决这个问题，Vuex允许我们将store分割成模块Module，每个模块拥有自己的state、mutations、actions、getters。

- 模块中的getters

  - getters定义的函数可以有第三个参数

  ![image-20220528162203427](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528162203427.png)

- 模块中的Actions
  - 有自己的参数context
  - context只在自己的模块中生效，相当于自己所在的模块
  - 在模块中才会有根的概念

- 对象的解构

  ![image-20220528194232897](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528194232897.png)

##### Vuex—store的项目结构

![image-20220528195844025](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220528195844025.png)

##### axios框架的基本使用

- axios（config）
- 网络模拟：httpbin.org/

-  默认axios传一个get请求

  ![image-20220530145048447](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220530145048447.png)

##### axios发送并发请求

- all方法的使用

  - 返回的是一个数组，使用axios.spread可将数组[res1,res2]展开为res1,res2

    ![image-20220530150031923](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220530150031923.png)

    ![image-20220530150402359](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220530150402359.png)

    ![image-20220530150446237](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220530150446237.png)

##### axios的配置信息相关

- 全局配置

  ![image-20220530153055013](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220530153055013.png)

  ![image-20220530153011771](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220530153011771.png)

##### axios的实例和模块封装

- 强调

  ![image-20220530155205856](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220530155205856.png)

- 进行网络封装的方式

  - 使用promise进行模块封装

  - 直接return

    - 因为interface本身返回的是一个Promise

      ![image-20220531203556814](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220531203556814.png)

      ![image-20220531203659717](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220531203659717.png)

      ![image-20220531204543418](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220531204543418.png)

##### axios拦截器的使用

- 请求拦截
  - config中的一些信息不符合服务器的要求
  - 每次发送网络请求时，都希望在界面中显示一个请求的图标
  - 某些网络请求（比如登录（token），必须携带一些特殊信息）

- 响应拦截

  - data是我们返回的数据

  ![image-20220531210943906](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220531210943906.png)

##### 项目创建和Github托管

































