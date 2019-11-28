# 伸缩布局(响应式布局或者弹性布局)

- **_背景_**：如果需要盒子在一行显示需要设置盒子浮动，但是浮动会带来一定影响；
- **_伸缩布局_**：采用伸缩布局可以不脱离文档流，并且使得盒子在一行排列

# 1 设置父元素为伸缩盒子(直接父元素)

- `display: flex`: 给父元素设置此属性；父元素就会变成伸缩盒子;伸缩盒子使得子元素盒子会在一行排列
- 问题：为什么在伸缩盒子中子元素会在一行显示？

```js
1. 子元素是按照伸缩盒子中主轴方向显示
2. 只有伸缩盒子才有主轴和侧轴
3. 主轴：默认从左向右显示
4. 侧轴：始终要垂直于主轴
```

```html
<!-- 示例1：display: flex; 伸缩盒子 -->
<style>
  .box {
    width: 300px;
    height: 300px;
    background: pink;
    outline: 1px solid gray;
    display: flex;
  }
  .son1 {
    width: 50px;
    height: 50px;
    background: red;
  }
  .son2 {
    width: 50px;
    height: 50px;
    background: greenyellow;
  }
  .son3 {
    width: 50px;
    height: 50px;
    background: blue;
  }
</style>

<div class="box">
  <div class="son1"></div>
  <div class="son2"></div>
  <div class="son3"></div>
</div>
```

## 1.2 设置伸缩盒子主轴方向

- `flex-direction`: 设置伸缩盒子主轴方向

* 备注：伸缩盒子默认的主轴方向是从左到右；只需要设置主轴的方向即可，因为侧轴会始终垂直于主轴

```css
flex-direction: row;
【默认值】/* 设置主轴方向：从左向右 */
flex-direction: row-reverse; /* 设置主轴方向：从右向左 */
flex-direction: column; /* 设置主轴方向：从上往下 */
flex-direction: column-reverse; /* 设置主轴方向：从下往上 */
```

```html
<!-- 示例1： -->
```

## 1.3 设置元素在主轴的对齐方式

- `justify-content`: 定义了浏览器如何分配顺着`父容器主轴`的弹性子元素之间及其周围的空间

```css
justify-content: flex-start; /* 从行首起始位置开始排列 */
justify-content: flex-end; /* 从行尾位置开始排列 */
justify-content: center; /* 居中排列 */
justify-content: start;
justify-content: end;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;
justify-content: stretch; /*【默认】拉伸*/
```

```html
<!-- 示例1： -->
<style>
  .box {
    width: 300px;
    height: 300px;
    background: pink;
    outline: 1px solid gray;
    display: flex;
    flex-direction: row;
    /* 设置子元素在伸缩盒子主轴的对齐方式 */
    justify-content: stretch;
  }
  .son1 {
    width: 50px;
    height: 50px;
    background: red;
  }
  .son2 {
    width: 50px;
    height: 50px;
    background: greenyellow;
  }
  .son3 {
    width: 50px;
    height: 50px;
    background: blue;
  }
</style>
```

## 1.4 设置元素在侧轴的对齐方式

- 在正常盒子中，子元素没有设置高度，则子元素是没有高度的
- 在伸缩盒子中，子元素没有设置高度，则默认子元素高度被拉伸到等于伸缩父盒子的高度

```css
align-items: flex-start; /* 在侧轴的开始位置开始排列 */
align-items: flex-end; /* 在侧轴的结束位置开始排列 */
align-items: center; /* 在侧轴的中间位置开始排列*/

align-items: stretch; /* 【默认】拉伸；所谓的拉伸是默认情况下子盒子在伸缩盒子的垂直方向高度等于父盒子高度*/
```

## 1.5 设置元素是否换行显示

- `flex-wrap: wrap;`
- 在伸缩盒子中，子元素默认都会在一行显示，并且不会换行
- 如果希望换行，给伸缩容器设置`flex-wrap: wrap;`

```html
<!-- 示例1： -->
<style>
  .box {
    width: 300px;
    height: 300px;
    background: pink;
    outline: 1px solid gray;
    display: flex;
    /* wrap：换行 ； nowrap不换行【默认】*/
    flex-wrap: nowrap;
  }
  .son1 {
    width: 50px;
    height: 50px;
    background: red;
  }
  .son2 {
    width: 200px;
    height: 50px;
    background: greenyellow;
  }
  .son3 {
    width: 100px;
    height: 50px;
    background: blue;
  }
</style>
```

## 1.6 设置换行后的对齐方式

- 备注：不只是设置换行后那行的对齐方式，而是换行后整体的对齐方式

```js
align-content: flex-start;
align-content: flex-end;
align-content: center;
align-content: space-around;
align-content: space-between;
align-content: stretch;【默认值】
```

```html
<!-- 示例1： -->
<style>
  .box {
    width: 300px;
    height: 300px;
    background: pink;
    outline: 1px solid gray;
    display: flex;
    /* wrap：换行 ； nowrap不换行【默认】*/
    flex-wrap: nowrap;
    align-content: flex-start;
    align-content: flex-end;
    align-content: center;
    align-content: space-around;
    align-content: space-between;
    align-content: stretch;
  }
  .son1 {
    width: 50px;
    height: 50px;
    background: rgb(31, 27, 27);
  }
  .son2 {
    width: 200px;
    height: 50px;
    background: greenyellow;
  }
  .son3 {
    width: 100px;
    height: 50px;
    background: blue;
  }
</style>
```
