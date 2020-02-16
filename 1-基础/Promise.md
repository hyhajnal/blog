## 关于 Promise

#### Promise

* pending（初始化）
* settled（完成）
  * fulfilled（成功）
  * rejected（失败）



#### Promise.all

并发执行

`then`  返回所有  `resolve` 数组（按参数的顺序）

`catch`   返回第一个 `reject` 的



#### Promise.race

`then` 返回最早完成的 `resolve`/ `reject`



#### Promise.allSettled

`then`  返回所有 `resolve`/ `reject`的数组



#### 场景

有并发数限制的 promise

串行执行的 promise

```
promises.reduce((a, b) => a.then(b))
```



https://segmentfault.com/a/1190000020848472

https://juejin.im/entry/5a69db996fb9a01caa20bb23