# css基础语法

### 兄弟选择器
- 要求: 有两个并列的div,当鼠标悬停在div-1时它的宽度增加200,同时div-2的宽度减少200
```html
<div class="container">
<div class="div-1"></div>
<div class="div-2"></div>
</div>
```
```css
.container {
  display: flex;
}

.div-1 {
  width: 200px;
  height: 100px;
  background-color: red;
  transition: width 0.3s ease;
}

.div-2 {
  width: 200px;
  height: 100px;
  background-color: blue;
  transition: width 0.3s ease;
}

.div-1:hover {
  width: 400px;
}

.div-1:hover ~ .div-2 {
  width: 0px;
}

```
