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