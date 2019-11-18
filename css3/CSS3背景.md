# 1 背景
## 1.1 背景透明

- `background: rgba(0,0,0,0.6);`：设置背景透明度

```html
<!-- 示例1： -->
<style type="text/css">
  body {
    background: #ccc url("./1.png") no-repeat fixed center 10px;
  }
  div {
    height: 400px;
    /*设置div盒子背景透明*/
    background: rgba(0, 0, 0, 0.6);
  }
</style>
```

## 1.2 背景大小
+ 背景：因为有时候图片太大无法放入小盒子，所以需要设置图片的大小
+ `background-size`: 设置背景图片的尺寸；
    - background-size: 100px 100px  // 设置成和盒子大小一样，但是会失真
    - background-size: cover  //等比例缩放，保证铺满屏幕（铺满不是平铺），有溢出的部分会被隐藏；因为等比例，所以可能图片显示不全。场景：需要背景图片随着浏览器缩小放大进行缩小放大
    - background-size: contain  //等比例缩放，将图片完成显示在盒子中，但是可能无法铺满盒子
```css
/* 示例1： */
<style type="text/css">
    body {
        background: #ccc url("./1.png") no-repeat fixed center 10px;
    }
    div {
        height: 400px;
        /*设置div盒子背景透明*/
        background: rgba(0,0,0,0.6);
        /*background-size设置的是插入图片的大小，一般的img通过width或者height设置*/
        /*尽量只设置一个值，防止图片失真*/
            /*background-size: 50%;  缩放为原来的一般*/
        /*background-size: cover; 等比例缩放，保证铺满屏幕，有溢出的部分会被隐藏*/
        /*background-size: contain; 等比例缩放，只要图片有一遍和盒子的宽度或者高度相等，图片就不再缩放 */
        background-size: 100px;
    }
</style>
```

## 1.3 设置背景相对原点位置
+ `background-origin`： 规定了指定背景图片background-image 原点位置的背景相对区域.
    - `background-origin: border-box`: 设置背景图片以边框左上角为原点（默认）
    - `background-origin: padding-box`: 设置背景图片以内边距左上角为原点
    - `background-origin: content-box`: 设置背景图片以内容区域左上角为原点
    - 备注：默认背景图片的原点是盒子的内边距左上角

+ 注意：当使用 background-attachment 为fixed时，该属性将被忽略不起作用


## 1.4 设置背景绘制区域
+ `background-clip`: 设置元素的背景（背景图片或颜色）是否延伸到边框下面
    - `border-box`: 背景延伸至边框外沿（但是在边框下层）。
    - `padding-box`: 背景延伸至内边距（padding）外沿。不会绘制到边框处。
    - `content-box`: 背景被裁剪至内容区（content box）外沿。
```html
<!-- 示例1： -->
<style type="text/css">
    * {
        padding: 0px;
        margin: 0px;
    }
    div {
    width: 300px;
    height: 300px;
    /* 注意这里 平铺  对background-clip的影响；如果是平铺则背景覆盖区域为边框+内边距+内容 */
    background: pink url("css/image/1.jpg") no-repeat;
    padding: 10px;
    border: 10px dashed red;
    /* background-clip: content-box; */
    /* background-clip: padding-box; */
    background-clip: border-box;
    }
</style>
```
## xxxxxxxxx雪碧图



