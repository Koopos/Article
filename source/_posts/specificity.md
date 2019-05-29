---
title: css 权重问题剖析
date: 2019-05-09 09:36:17
tags:
---

## 1.css权重出现原因

---

css 是层叠样式，当多个样式同时作用于一个元素时，如果属性名称不同，大家都可以相安无事一同改变同一个元素。然而如果多条规则的属性名称相同就出现规则冲突的问题。


那么如何解决这种问题呢？css 引入了权重的概念，每条规则都有其作用的元素及权重，权重大的规则会生效，权重小的则被忽略。


## 2.四种权重类型

---

- 行内样式  => 1000
- id  => 100
- 属性、类名、伪类  => 10
- 元素，伪元素  => 1


```javascript
  <div class="message">
    <!--行内样式权重为 1000-->
    <div class="message__title" id="m-title" style="color:black">标题</div>
    <div class="message__content"></div>
  </div>

  <style>
  #m-title {
    color: lightblue; //权重:100
  }
  .message .message__title { 
    color: green;  //权重:11
  }
  .message__title {
    color: red; //权重:10
  }


  </style>

```

## 3. 特殊的 `！important`
---
`!important` 是特殊的权重，优先级最高，用户定义的`!important`的优先级高于服务器定义的。






