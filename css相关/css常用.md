#### 换行展示

```
white-space: pre-line;
```



#### fixed 的坑

一般fixed的元素是相对于可视区定位的，但当父级/祖先元素是transform时，定位就会失效，相当于absolute定位



#### 吸顶

[vue directive](https://raw.githubusercontent.com/rguanghui/vue-sticky/master/src/index.js)

* IOS无法监听滚动事件（可监听touchmove事件）
* sticky相对于父级容器定位