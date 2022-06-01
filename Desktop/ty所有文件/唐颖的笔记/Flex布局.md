##### Flex布局

- 开启flex布局：设置display属性为flex或inline-flex

   - flex：块级元素，换行显示
   - inline-flex：行内元素，可以和其他 元素在同一行显示

- flex布局模型

   ![image-20220403195129654](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220403195129654.png)

- 应用在flex-container上的CSS属性

   - flex-direction
     - 决定主轴的方向
     - flex items默认都是沿着main axis（主轴）从main start开始往main end方向排布。
     - row（默认值）：主轴从左到右
     - row-reverse：主轴从右到左
     - column：主轴从上到下
     - column-reverse：主轴从下到上
   - justify-content
     - 决定flex items在main axis的对齐方式
     - flex-start（默认值）：与main start对齐
     - flex-end:与main end对齐
     - center：居中对齐
     - space-between:
       - flex items之间的距离相等
       - 与main start、main end两端对齐（两边没距离）
     - space-evenly（平分）:
       - flex item之间的距离相等
       - flex items与main start、main end之间的距离等于flex items之间的距离（所有距离平均分，包括两边距离）
     - space-around（部分平分）:
       - flex items之间的距离相等
       - flex items与main start、main end之间的距离是flex items之间距离的一半（两边距离等于中间距离的一半）
   - align-items
     - 决定了flex items在cross axis上的对齐方式
     - normal：在弹性布局中，效果和stretch一样
     - stretch：当flex items在cross axios方向的size为auto时，会自动拉伸填充至flex container
     - flex-start：与cross start对齐，以下都是在没设置height的情况下才有效果
     - flex-end：与cross end对齐
     - center：在cross axis上居中对齐
     - baseline：与基准线对齐（指第一行文本）
   - flex-wrap
     - 决定flex container是多行还是单行
     - 默认情况下，所有的flex items都会在同一行显示
     - nowrap（默认）：不换行
     - wrap：换行
     - wrap-reverse：多行（反转）
   - flex-flow
     - flex-direction||flex-wrap的缩写属性
   - align-content
     - 决定了多行flexitems在cross axis上的对齐方式
     - stretch（默认值）：与align-items的stretch类似
     - flex-start：与cross start对齐
     - flex-end：与cross end对齐
     - center：居中对齐
     - space-between：
       - flex items之间的距离相等
       - 与cross start、cross end两端对齐
     - space-around：
       - flex items之间的距离相等
       - flex items与cross start、cross end之间的距离是flex items之间距离的一半
     - space-evenly：
       - flex items之间的距离相等
       - flex items与cross start、cross end之间的距离是flex items之间的距离（平分）

- flex items

   - order

     - 决定flex items的排布顺序
     - 可以设置任意整数，值越小越排在前面
     - 默认值是0

   - align-self

     - 可以通过align-self覆盖父元素flex container设置的align-items
     - auto（默认值）：遵从flex container的align-items设置
     - stretch、flex-start、flex-end、center、baseline，效果跟align-items一致

   - flex-grow

     -  决定了flex items如何扩展
     - 可以设置非负数字（正小数、正整数、0），默认值是0
     - 当flex container在main axios方向上有剩余size时，flex-grow属性才会有效
     - 如果flex-items的flex-grow总和sum超过1，每个flex items扩展的size为flex container的剩余size*(flex-grow/sum)
     - 如果flex-items的flex-grow总和sum不超过1，每个flex items扩展的size为flex container的剩余size*flex-grow
     - flex items扩展后的最终size不能超过max-width\max-height

   - flex-shrink

     - 决定了flex items如何收缩
     - 可以设置任意非负数字，默认值是1
     - 当flex items在main axis方向上超过了flex containerde size，flex-shrink属性才会有效
     - 如果所有flex items的flex-shrink总和超过1，每个flex item收缩的size为
       - flex items超出flex container的size*（收缩比例/所有flex items的收缩比例之和）
     - 如果所有flex items的flex-shrink总和sum不超过1，每个flex item收缩的size为
       - flex items超出flex container的size* sum*(收缩比例/收缩比例之和）
       - 收缩比例=flex-shrink*flex item的base size
       - base size就是flex item放入flex container之前的size
     - flex items收缩后的最终size不能小于mid-width\mid-height

   - flex-basis

     - 用来设置flex items在主轴方向上的大小
       - auto（默认值）、具体的宽度数值
     - 决定flex items最终大小的因素，优先级从高到低
       - max-width\max-height\min-width\min-height
       - flex-basis
       - width\height
       - 内容本身的size

   - flex

     ![image-20220404105321047](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220404105321047.png)

- 附：

  - 下面代码表示文字居中

    ![image-20220404150816717](C:\Users\86189\AppData\Roaming\Typora\typora-user-images\image-20220404150816717.png)

  - 表示盒子居中：margin：0 auto；



--------20110404