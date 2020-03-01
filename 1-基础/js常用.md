检查数组中有没有包含某一个元素

```js
[1,2,3,4].includes(1)  // true
```



获取url中的参数

```
export function getQueryString(key){
  const reg = new RegExp("(^|&)"+key+"=([^&]*)(&|$)");
  const result = window.location.search.substr(1).match(reg);
  return result?decodeURIComponent(result[2]):null;
}
```



生成UUID（全局唯一标识符）128位

时间戳+机器码+进程码+自增数

```js
function guid() {
    function S4() {
       return (((1+Math.random())*0x10000)|0).toString(16).substring(1);
    }
    return (S4()+S4()+"-"+S4()+"-"+S4()+"-"+S4()+"-"+S4()+S4()+S4());
}
//"52f18225-6f71-1c17-bb68-01f40fdfd62f"
```



运算符优先级

https://github.com/xhlwill/blog/issues/16



浏览器返回不刷新

```
方法1：
window.addEventListener('pageshow', () => {
  if (e.persisted || (window.performance && 
    window.performance.navigation.type == 2)) {
    location.reload()
  }
}, false);

方法2:
window.history.replaceState(null, '', window.location.href + '?timestamp=' + new Date().getTime());
```





