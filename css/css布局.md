# 1. clear
+ 定义：clear属性规定元素的哪一侧不允许其他浮动元素
+ 语法：`clear : none | left | right | both`
+ 作用：常用于清除浮动

# 2. overflow
+ 定义：overflow 属性规定当内容溢出元素框时发生的事情；定义溢出元素内容区的内容会如何处理
+ 语法：`overflow : visible | auto | hidden | scroll`
    - visible: 不剪切内容也不添加滚动条。默认值
    - auto：由浏览器决定是否增加滚动条处理
    - hidden：不显示超过对象尺寸的内容
    - scroll：总是显示滚动条
+ 作用：也可用于清除浮动

# 3. display
+ 定义：规定元素应该生成的框的类型
+ 备注："display" 属性来创建不占据页面空间的不可见元素
+ 语法：`display: inline-block | block | none | inline`
    - block : 块对象的默认值
    - none : 隐藏对象。与visibility属性的hidden值不同，其不为被隐藏的对象保留其物理空间;设置为 none 会将元素从可访问性树中移除；此时在浏览器上就看不见标签了
    - inline : 转成行内元素

# 4. visibility
+ 定义：规定元素是否可见；（即使不可见的元素也会占据页面上的空间; 而display：none；创建的不可见元素是不占据页面空间的）
+ visibility指定是否显示一个元素生成的元素框。这意味着元素仍占据其本来的空间，不过可以完全不可见
+ 语法：`visibility : inherit | visible | collapse | hidden`
    - inherit : 　继承上一个父对象的可见性
    - visible : 　对象可视
    - hidden : 　对象隐藏
    - collapse : 　主要用来隐藏表格的行或列。隐藏的行或列能够被其他内容使用。对于表格外的其他对象，其作用等同于hidden。IE5.5尚不支持此属性