## Typescript常用写法

#### 解构

```
  let { a : name1 , b : name2 } : { a : string, b : number }= { a : 'a' , b : 100 };
```



#### 对象

```js
// 动态属性
Record<string, []>

formData: {
	[propName: string]: {
		[propName: string]: any;
	}
}
```

