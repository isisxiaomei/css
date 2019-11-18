# 背景样式

- 默认情况下背景颜色`background-color`覆盖的范围是`元素内容 + 内边距 + 边框`；
- 默认`不平铺`的情况下背景图片`background-image`覆盖的范围是`元素内容 + 内边距`
- 如果设置图片平铺属性，则背景区域覆盖范围是：`元素内容 + 内边距 + 边框`，并且边框显示在上层

# 1. background-color

- `background-color`: 设置元素的背景颜色

```css
/* 示例1： */
background-color: pink;
background-color: #ff0033;
background-color: rgb(255, 0, 0);
background-color: rgba(255, 0, 0, 0.1);
```

# 2. background-image

- `background-image`: 给元素设置一张或多张背景图
  - 注意：先指定的图像会在之后指定的图像上面绘制。因此指定的第一个图像“最接近用户”
  - 如果一个指定的图像无法被绘制 (比如，被指定的 URI 所表示的文件无法被加载)，浏览器会将此情况等同于其值被设为 none

```css
/* 示例1： */
div {
  width: 400px;
  height: 500px;

  background-image: url("./Snipaste_2019-08-24_21-08-56.png");
  /* 注意顺序不同背景层叠不同： 先指定的在最上面*/
  background-image: url("../../media/examples/lizard.png"),
    url("../../media/examples/star.png");
  background-image: url("../../media/examples/star.png"),
    url("../../media/examples/lizard.png");
}
```

# 3. background-repeat

- `background-repeat`: 控制背景图片的重复方式；默认是平铺
  - no-repeat：不平铺，
  - repeat-x：水平平铺；
  - repeat-y：垂直平铺；
  - repeat: 重复；(默认)

# 4. background-position

- `background-position`: 设置背景图的位置；默认的背景位置值是(0,0)。
  - 注意 1：如果背景图片的大小和容器一样，那设置百分比的值将永远无效，因为“容器和图片的差”为 0（图片永远填满容器，并且图片的相对位置和容器的相对位置永远重合）。在这种情况下，需要为偏移使用绝对值（例如 px)
  - 注意 2：百分比是图片相对于容器来说的。`0%(图片的左边界与容器左边界重合); 100%(图片的右边界与容器右边界重合); 50%(代表图片的中点和容器的中点重合)`
  - 注意 3：像素是图片相对于容器左边界为 0px。`0px（图片的左边界与容器左边界重合）-10px(图片从容器左边界左移10px)`
  - 方式 1(方位名词)：`top, left, bottom, right, center`: 其中的一个用来指定把 item 放在哪一个边缘。另一个维度被默认设置成 50%居中
  - 方式 2(精确坐标 x, y)：`0px（图片的左边界与容器左边界重合）-10px(图片从容器左边界左移10px)`
  - 方式 3(混搭或者 4 值语法): `background-position: top 20px right 30px;`

```css
/*  示例1： */
 <style type="text/css">
    body {
        background: #ccc;
    }
    div {
        width: 400px;
        height: 500px;
        /*设置div这个块的背景*/
        background-color: pink;

        /*图片是否平铺：默认是平铺；no-repeat不平铺，repeat-x：水平平铺；repeat-y：垂直平铺*/
        background-repeat: no-repeat;


        /*第一种利用方位名词：利用方位名词：左下角；控制位置：访问名词没有顺序；如果只写一个方位名词另一个则默认center*/
        background-position: left bottom;
        /*第二种利用精确坐标  x y坐标，顺序不能颠倒*/
        background-position: 100px 200px;
        /*第三种 混搭 水平x10  垂直方向居中；*/
        background-position: 10px center;
        /* x：10px，y：50% */
        background-position: 10px 50%;
        /* 4值语法：图片距上边界20px, 距右边界 30px */
        background-position: top 20px right 30px;
    }
</style>
```

# 5. background-attachment

- `background-attachment`：设置背景图像的位置是在视口内固定，还是随着包含它的区块滚动

```css
/* 示例1： */
div {
  width: 400px;
  height: 500px;
  /*scroll: 默认背景图片是滚动的，fixed，背景图片固定*/
  background-attachment: scroll;
  /*背景简写：background: 背景颜色 背景图片地址 背景平铺 背景滚动 背景位置*/
  background: #ccc url("css/image/1.jpg") no-repeat fixed center 10px;
}
```

# 6. 背景简写

- `background`: 属性被指定多个背景层时，使用逗号分隔每个背景层
- 一个元素可以设置多重背景图片
- 每组属性间用逗号隔开
- 背景图片之间存在交集，前面的背景图会覆盖在后面的背景图之上
- 避免背景色将图片盖住，一般在最后一组背景图设置背景颜色

```css
/* 示例1： */
div {
  width: 400px;
  height: 500px;
  /*背景简写：background: 背景颜色 背景图片地址 背景平铺 背景滚动 背景位置*/
  background: #ccc url("./1.png") no-repeat fixed center 10px;

  background: url("./1.png") no-repeat fixed left top,
                url("./1.png") no-repeat fixed left top,
                url("./1.png") no-repeat fixed left bottom pink;
}
```


