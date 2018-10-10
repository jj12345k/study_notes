# es6 数组新特性

## 新方法和属性
### Array.from
> Array.from 将类数组对象 和 具有可遍历（iterable）的对象 转换为数组(Map 和 Set 数据结构)

类数组对象：key 是数字下标 同时具有length 属性
```javascript
    //类数组对象
    let arrayLike = {
        '0': 'a',
        '1': 'b',
        '2': 'c',
        length: 3
    };
```
### Array.of 可将一组值转换为数组
> Array.of(1,2,3,4);

### find() 找出数组中第一个符合条件的元素
> [22,55,88].find(item => item> 50);

### findIndex() 找出数组中第一个符合条件的元素的下标索引
> [22,55,88].findIndex(item => item> 50);

### entries()，keys()和values()
> 用于遍历数组。它们都返回一个遍历器对象，可以用for...of循环进行遍历

### contains() 方法
> 用于检测数值中是否含有给定的值

<style>
    *{ font-family:微软雅黑; }
</style>