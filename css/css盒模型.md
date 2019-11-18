# 1 内边距
+ padding: 内边距（简写顺时针）
```html
<style type="text/css">
  div {
    width: 100px;
    height: 100px;
    border: 10px solid red;
    /*内容距离上边框10px*/
    padding-top: 10px;
    /*如果只写一个值，上下左右都是20px*/
    padding: 20px;
    /*padding两个值，表示上下10px，左右30px*/
    padding: 10px 30px;
    /*表示上10，左右30，下50*/
    padding: 10px 30px 50px;
    /*简写表示：顺时针，上右下左*/
    padding: 10px 20px 30px 40px;
  }
</style>
```
# 2 外边距
+ margin: 外边距（使用和内边距相似）

# 3. 问题类
## 3.1 背景图片和图片
+ 使用场景
    - 产品展示用插入图片
    - 背景图片适合做一些小图标
```html
<!-- 混淆1：文字水平居中和盒子水平居中的区别 -->
div {
            width: 100px;
            height: 100px;
            text-align: center; /*文字水平居中*/
            margin: 10px auto;  /*盒子水平居中*/
    }

<!-- 混淆2：插入图片和背景图片的区别（简单说插入的img其实是个盒子） -->
    <style type="text/css">
        section img {
            /*插入的图片会把文字挤到一遍*/
            width: 10px;
            height: 20px;       /*插入图片的大小通过width和height调控*/
            margin: 10px 20px;  /*插入图片的位置通过margin调控*/
        }
        aside {
            /*注意背景图片不影响块上面字的显示*/
            width: 400px;
            height: 400px;
            border: 1px solid red;
            background: #fff url("./Snipaste_2019-08-24_21-08-56.png") no-repeat;
            background-size: 200px 200px; /*背景图片更改大小 只能用background-size不能用width和height*/
            background-position: 30px 50px;  /*背景图片更改位置只能用 background-position*/
        }
    </style>
```
## 3.2 清除内外边距
+ 因为浏览器有默认的margin是8px，并且各个浏览器的默认都不一样，故我们需要全部清楚默认的内外边距样式
+ 行内元素只有左右内外边距，没有上下内外边距，所以行内元素只需要指定左右内外边距
```css
/* //清除默认内外边距样式 */
* {
    padding: 0px,
    margin: 0px
}
/* //经常采用 */
div,h1,h2,h3,h4p,input,textare {
    padding: 0px,
    margin: 0px
}
```

## 3.3 块元素垂直合并问题
+ 只有垂直方向有外边距合并问题，水平方向没有
+ 这种情况避免的办法是：只设置一个盒子，免得分赃不均
```css
/* 示例1： */
    <style type="text/css">
        div {
            width: 200px;
            height: 200px;
            background: pink;
        }
        /*此时下面两个div块发生了：外边距合并，垂直的块盒子，合并后的外边距以最大的外边距为准
        解决办法：只设置一个盒子的外边距就行
        */
        div:first-child {
            margin-bottom: 30px;
        }
        div:last-child {
            margin-top: 10px;
        }
    </style>
```
## 3.4 嵌套块元素塌陷问题
+ ***问题背景***：比如两个div嵌套，如果给子块元素一个margin-top=30(或者给父元素一个margin-top=30),此时整个父块元素跟子块元素会整体向下平移30，这种称为塌陷。
```js
//解决塌陷的3个办法：
1. 给父块元素定义一个1像素的上边框（border=1px solid red）
2. 给父元素定义一个1像素的上内边距（padding=1px）
3. overflow: hidden
```
