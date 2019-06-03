---
title: css counter 使用
date: 2019-05-09 11:39
tags: css 
---

## 1.css3有个新的功能counter

---

ul,ol 两种列表有其局限性，比如不能自定义起始值，不能指定 step，不能自定义序号的文案。counter 出现就是为了解决类似需求。

## 2.两个常用的属性

---

- counter-reset 定义一个计数器
- counter-increment 操作哪一个计数器，设置 step 为多少

```css 

  .counter {
    counter-reset: htag 1 ctag 2; //起始值 
  }

  h1 {
    counter-increment: htag 2 ctag 3; //counter名称 ，这个可以操作多个计数器
  }
  h1::before {
    content: counter(htag) "."
  }
```

```html 
  <div class="counter">
    <h1>qeqwe</h1>
    <h1>qweqwe</h1>
  </div>
```

## 3.有趣用途
---

- 可以用纯 css 实现计算表单校验错误的数目 （invalid 伪类）

- 可以统计一共有多少章节
