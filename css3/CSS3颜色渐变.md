# 新特性颜色渐变

# 1 线性渐变
## 1.1 基本使用
- 线性渐变 3 要素：
  - 1. 开始颜色和结束颜色
  - 2. 渐变方向
  - 3. 渐变范围
- 表示渐变方向：
  - 1. `to + right | top | left | bottom`
    - `to left top`: 从右下到左上角渐变
  - 2. 通过角度表示方向（12 点钟为 0 度，顺时针旋转）
    - `0deg`：【从下往上】
    - `90deg`: 【从左向右渐变】
+ `linear-gradient(方向, 开始颜色, 结束颜色)`
```css
/* 示例1：线性渐变 */
.box {
    height: 200px;
    /* 从左到右，开始颜色红色，结束颜色蓝色 */
    background-image: linear-gradient(to right, red, blue);
    background-image: linear-gradient(0deg, red, blue);
}
<div class="box"></div>
```

```css
/* 示例2：线性渐变 */
<style type="text/css">
      .box {
        height: 300px;
        /* red 20%, 表示从20%开始渐变, 那20%以前都是红色， */
        background: linear-gradient(
          135deg,
          red 20%,
          blue 20%,
          blue 40%,
          red 40%,
          red 60%,
          blue 60%,
          blue 80%,
          red 80%
          );

        background-size: 200px;
      }
    </style>
<div class="box"></div>
```

```css
/* 示例1：对角线渐变 */
.box {
        height: 300px;
        /* 对角线，从右下到左上角渐变， */
        background: linear-gradient(
          to left top,
          red,
          blue
          );
      }
```
## 1.2 使用多个颜色结点
+ 多颜色节点均匀分布；也可以通过设置百分比使其不均匀分布
+ 有兼容问题是，标准语法必须放在最后面
```css
/* 示例1： */
.box {
        height: 300px;
        background: linear-gradient(to right, red,orange,yellow,green,blue,indigo,violet);
}

/* 示例2： */
#div {
    height: 200px;
    background: -webkit-linear-gradient(red 10%, green 85%, blue 90%); /* Safari 5.1 - 6.0 */
    background: -o-linear-gradient(red 10%, green 85%, blue 90%); /* Opera 11.1 - 12.0 */
    background: -moz-linear-gradient(red 10%, green 85%, blue 90%); /* Firefox 3.6 - 15 */
    background: linear-gradient(red 10%, green 85%, blue 90%); /* 标准的语法（必须放在最后） */
}
```
## 1.3 线性渐变透明度
+ 
```css
/* 示例1： */
.box {
        height: 300px;
        /* 颜色从透明渐变到有颜色 */
        background: linear-gradient(to right, rgba(21, 173, 15, 0), rgba(21, 173, 15,1));
      }
```
## 1.4 重复线性渐变
+ `repeating-linear-gradient()`: 函数用于重复线性渐变


# 2 径向渐变
- 由它们的中心开始向外扩散
- 径向渐变3要素
    - 1. 半径
    - 2. 圆心位置
    - 3. 开始颜色，结束颜色
## 2.1 基本使用
```css
/* 示例1： */
<style type="text/css">
    .box {
    height: 300px;
    width: 300px;
    margin: 100px auto;

    background-image: radial-gradient(
        /* 半径100px， at center 圆心位置 */
        /* 开始颜色red，结束颜色blue */
        100px at center,
        red,
        blue
    );
    }
</style>
<div class="box"></div>
```
