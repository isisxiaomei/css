# 1 box-sizing

- CSS3 中可以选择使用旧的盒子模型或者使用 CSS3 的新盒子模型
- `box-sizing` : 用于计算元素宽度和高度的默认的 CSS 盒模型
  - `box-sizing:border-box;`: 采用 CSS3 的新盒子模型
  - `box-sizing: content-box;`(默认值): 表示采用 w3c 的标准盒子模型，padding 和 border 会撑开宽度
- CSS3 中的新盒子模型，paading 和 border 都不会撑开盒子；换句话说，盒子大小为 width，paading 和 border 是包含在 width 里面。
- 注意：这里不包含外边距

```html
<!-- 示例1： -->
<style type="text/css">
  div {
    width: 160px;
    height: 80px;
    padding: 20px;
    border: 8px solid red;
    margin: 10px;   /* 注意盒子不包含外边距 */
    background: yellow;
  }
  .content-box {
    box-sizing: content-box;
  }
  .border-box {
    box-sizing: border-box;
  }
</style>
<div class="content-box">Content box</div>
<br />
<div class="border-box">Border box</div>
```
