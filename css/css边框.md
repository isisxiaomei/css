# 边框

- `border`设置元素的整体边框样式

# 1. border-width

- `border-width`: 表示边框粗细
- `border-width`：是 border-top-width, border-right-width, border-bottom-width, 和 border-left-width 的简写(顺时针：上右下左)
  - `border-width: thin;` 细边线
  - `border-width: medium;` 中等边线
  - `border-width: thick;` 宽边线

```css
/* 示例1： */
/* 表示：上1 左右2 下1.5  粗细*/
border-width: 1px 2em 1.5cm;
/* 上右下左 粗细*/
border-width: 1px 2em 0 4rem;
```

# 2. border-color

- 设置边框颜色

# 3. border-style

- `border-style`: 设置边框线样式
  - none: 没有边框
  - solid: 实线（最常用）
  - dashed: 虚线
  - double: 双实线
  - dotted: 点线

# 4. border 简写

- `border: 10px solid pink;`: 边框粗细 样式 颜色
- `border-bottom: 2px dotted blue;`

```html
<!-- 示例1： -->
<style type="text/css">
  .div1 {
    width: 100px;
    height: 500px;
    border-width: 10px; /*设置边框粗细*/
    border-color: red; /*设置边框颜色*/
    /*设置边框线：none没有边框；solid大实线（最常用）；dashed虚线；double双实线；dotted点线*/
    border-style: solid;
  }
  input {
    /*border-top设置上边框*/
    border-top-width: 10px;
    border-top-color: red;
    border-top-style: dashed;
  }
  div {
    /*边框简写：边框粗细 样式(什么线条) 颜色 */
    border-top: 1px solid red;
    border-bottom: 2px dotted blue;
    /*对边框整体设置简写（不分上下左右）*/
    border: 10px solid pink;
  }
  /*表格单元格边框合并*/
  .div2 {
    /*边框合并：表格的边框和单元格的边框合并边框线变粗1+1=2，这时候配置border-collapse: collapse
        可以将单元格和表格相邻的边框线合并1+1=1*/
    border-collapse: collapse;
  }
</style>
```
