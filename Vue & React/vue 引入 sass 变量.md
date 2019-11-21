## vue 引入sass变量

vue 统一管理 sass 变量

#### 第一种方式

每个组件需要单独写import

``` 
<style lang="scss">
// 引入sass全局变量
@import '../styles/common.scss';

// other code
</style>
```

#### 第二种方式

**sass-resources-loader**

修改 build/utils.js

```
scss: generateLoaders('sass').concat(
  {
    loader: 'sass-resources-loader',
    options: {
      resources: path.resolve(__dirname, '../src/style/_variables.scss')
    }
  }
),
```

在这个文件里，为了避免在最终编译后的文件中出现重复的 CSS，建议只包含变量、mixins 等

https://github.com/vuejs/vue-loader/blob/master/docs/zh-cn/configurations/pre-processors.md