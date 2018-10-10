# ES3 ES5/6 jquery 对比
**知识点**

> **in 和 hasOwnProperty 区别**
> - in 判断的是对象中是否存在对应属性(实例、原型均可)
> - obj.hasOwnProperty() 判断的是实例对象中是否存在对应属性

> **JSON.stringify() 和 JSON.parse()**
> - JSON.stringify() 将json对象转换为json字符串
> - JSON.parse() 将json字符串转换为json对象，注意json字符串必须为标准格式

## - 对象部分

**[预定义的对象]**
```
    var defaults = {
        name: "jack",
        age: 12,
        sex: "男"
    };

    var options = {
        name: "lily",
        job: "teacher"
    };
```

### 对象遍历
#### 需求：[遍历输出对象中的属性]
```
    //传统

    // for in 说明：循环遍历对象自身的和继承的可枚举属性
    for(var key in options){
        if(options.hasOwnProperty(key)===true){
            console.log(key,options[key]);
        }
    }

    //jquery 遍历
    $.each(options,function(key,val){
        console.log(key,val);
    });

    // es5 遍历
    Object.entries(options).forEach(function(item){
        console.log(item[0],item[1]);
    });
```

### 


<style>
    *{ font-family:微软雅黑; }
</style>