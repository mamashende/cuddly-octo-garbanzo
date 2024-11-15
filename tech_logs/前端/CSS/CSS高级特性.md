多个选择器之间的优先级

选择器的重写复用与继承

更多图形性质：
不同的box

对于一个带有几何形状要求的标签
可以有如下性质：
```css
.a {

width: 100%;

padding: 1em;

border: 3px solid #ccc;

}

  

.b {

box-sizing: border-box;

width: 100%;

padding: 1em;

border: 3px solid #ccc;

}
```
width用于描述一个矩形的基本大小性质
boder是矩形外沿边的宽度，可以自定义上下左右边不同，也可以统一
padding是boder内沿到容纳文字标签内容的矩形的宽度，同样可以自定义上下左右不同宽度的情况
同时box-sizing设定为border-box时，width表示的是标签本体的大
小，不加这个的话，就是文字内容矩形的大小

IFC
BFC



flex box
更灵活的单一方向的布局属性


grid
灵活二维布局

float


position
box定位

absolute

fixed

