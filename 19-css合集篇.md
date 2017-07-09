## rgba()和opacity的透明效果有什么不同？

`rgba()`和`opacity`都能实现透明效果。

`rgba()`

​	只作用于设置了`rgba()`的元素的颜色或者其背景色。（设置rgba透明的元素的子元素不会继承透明效果！）

`opacity`

​	作用于元素，以及元素内的所有内容的透明度。

---



## 描述一个”reset”的CSS文件并如何使用它。知道normalize.css吗？你了解他们的不同之处？

重置样式非常多，凡是一个前端开发人员肯定有一个常用的重置CSS文件并知道如何使用它们。他们是盲目的在做还是知道为什么这么做呢？原因是不同的浏览器对一些元素有不同的默认样式，如果你不处理，在不同的浏览器下会存在必要的风险，或者更有戏剧性的性发生。

你可能会用Normalize来代替你的重置样式文件。它没有重置所有的样式风格，但仅提供了一套合理的默认样式值。既能让众多浏览器达到一致和合理，但又不扰乱其他的东西（如粗体的标题）。

在这一方面，无法做每一个复位重置。它也确实有些超过一个重置，它处理了你永远都不用考虑的怪癖，像HTML的audio元素不一致或line-height不一致。

---



## Sass、LESS、stylus是什么？大家为什么要使用他们？

> 他们是CSS预处理器。他是CSS上的一种抽象层。他们是一种特殊的语法/语言编译成CSS。

- 为什么要使用它们？
  - 结构清晰，便于扩展。
  - 可以方便地屏蔽浏览器私有语法差异。这个不用多说，封装对浏览器语法差异的重复处理，减少无意义的机械劳动。
    可以轻松实现多重继承。
  - 完全兼容 CSS 代码，可以方便地应用到老项目中。LESS 只是在 CSS 语法上做了扩展，所以老的 CSS 代码也可以与 LESS 代码一同编译。

---



## margin和padding分别适合什么场景使用？

**margin是用来隔开元素与元素的间距；padding是用来隔开元素与内容的间隔。**
何时使用margin：

1. 需要在border外侧添加空白。
2. 空白处不需要背景色。
3. 上下相连的两个盒子之间的空白，需要相互抵消时。

何时使用padding：

1. 需要在border内侧添加空白。
2. 空白处需要背景颜色。
3. 上下相连的两个盒子的空白，希望为两者之和。

兼容性的问题：在IE5 IE6中，为float的盒子指定margin时，左侧的margin可能会变成两倍的宽度。通过改变padding或者指定盒子的display：inline解决。

---



## overflow: scroll时不能平滑滚动的问题怎么处理？

1. 高度尺寸不确定的时候，使用：overflow-y：scroll;
2. 高度尺寸确定的，要么没有滚动条，要么直接出现，不会出现跳动。
3. css3计算calc和vw单位巧妙实现滚动条出现页面不跳动。

```css
.wrap-outer {
margin-left: calc(100vw - 100%);
}
```

或

```css
.wrap-outer {
padding-left: calc(100vw - 100%);
}
```

首先，.wrap-outer指的是居中定宽主体的父级，如果没有，创建一个，然后，calc是css3的计算。
100vw是浏览器的内部宽度，而100%是可用宽度，不含滚动条。
calc（100vw-100%）是浏览器的滚动条的宽度。

---

## 有一个高度自适应的div，里面有两个div，一个高度100px，希望另一个填满剩下的高度。

```css
<div class="box">
    <div class="el1"></div>
    <div class="el2"></div>
</div>
.box {width:200px; height: 100%;background:red;position:relative;}
.el1 {height:100px;background:green;}
.el2 {background:blue;width:100%;position:absolute;top:100px;bottom:0;}
```

外层`position: relative`；
百分百自适应元素直接`position: absolute; top: 100px; width:100%;bottom: 0; left: 0`,原理就是用absolute的元素同时设置top和bottom（或同时设置left和right）来拉伸元素，从而达到高度（宽度自适应）

---

## 如何修改chrome记住密码后自动填充表单的黄色背景 ？

```css
input:-webkit-autofill, textarea:-webkit-autofill, select:-webkit-autofill {
    background-color: rgb(250, 255, 189); /* #FAFFBD; */
    background-image: none;
    color: rgb(0, 0, 0);
}
```

---

## 怎么让Chrome支持小于12px 的文字？

1. 用图片：如果是内容固定不变情况下，使用将小于12px文字内容切出做图片，这样不影响兼容也不影响美观。
2. 使用12px及12px以上字体大小：为了兼容各大主流浏览器，建议设计美工图时候设置大于或等于12px的字体大小，如果是接单的这个时候就需要给客户讲解小于12px浏览器不兼容等事宜。
3. 继续使用小于12px字体大小样式设置：如果不考虑chrome可以不用考虑兼容，同时在设置小于12px对象设置-webkit-text-size-adjust:none，做到最大兼容考虑。
4. 使用12px以上字体：为了兼容、为了代码更简单 从新考虑权重下兼容性。

---

