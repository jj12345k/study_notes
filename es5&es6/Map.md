# Map 集合 专题

概念：Map 是键值对的集合（Hash 结构），es6 中的一种新的数据结构，类似于 对象！
说明：Map 部署了 iterator 接口，可以使用 for of 循环遍历 map

## map 具有的属性和方法
> map 具有的方法和属性
> - size 获取 map 集合元素个数
> - set() 向集合中添加新元素
> - get() 获取指定 key 的元素值
> - delete() 删除指定元素
> - has() 判断是否存在指定元素
> - clear() 清空所有元素
> - keys() 返回 MapIterator key 值
> - values() 返回 


## map 和 数组比对
```javascript
    let map =new Map();
    let arr =[];

    map.set("name","jack");
    arr.push({"name":"jack"});

    //删
    map.delete("name");
    
    var _index =arr.findIndex(item => item.name && item.name =="jack");
    arr.splice(_index,1);

    //改
    map.set("name","lucy");

    var _index  =arr.findIndex(item => item.name && item.name =="jack");
    arr[_index] ={"name":"lucy"};

    //查
    map.has("name");
    arr.findIndex(item => item.name && item.name =="jack")

    //遍历
    for(var item of map){
        console.log(item); // [key,value]
    }

    for(var item of arr){
        console.log(arr);
    }
```


<style>
    *{ font-family:微软雅黑; }
</style>