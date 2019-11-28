# 1. 文字水平居中
+ `text-align`：在父元素上设置 text-align: center 使文字/图片水平居中


# 2. 文字垂直对齐
+ `vertical-align`

# 3. 盒子水平居中
+ 盒子水平居中：
    - 1. 必须是块级元素
    - 2. 盒子必须指定宽度；然后左右给为auto就可实现盒子水平居中
```css
/* 示例1： */
.container {
  width: 80%;
  margin-left: auto;
  margin-right: auto;
}
```
# 4 绝对定位水平居中问题
+ `margin:0 auto;` 只能让`标准流`的盒子居中对齐，但是加了绝对定位的盒子margin-auto水平居中无效
+ 定位盒子水平垂直居中算法：
```js
1. 首先left 50% 父盒子的一半大小
2. 然后走自己盒子外边距负的一半值 margin-left
```


https://blog.csdn.net/qq_27576607/article/details/78697812