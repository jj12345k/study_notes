# ES3 ES5/6 jquery 对比

## - 数组部分

**[预定义的数组]**
```javascript
    var colors = ["red", "yellow", "blue", "green"];
    var nums = [11, 22, 33, 44, 55, 23];
```
------

### 数组遍历
#### 需求：[遍历输出数组中的元素]
```javascript
    //传统遍历
    for(var k in nums){
        console.log(k,box[k]);
    }
    
    //jquery遍历
    $.each(nums,function(k,v){
        console.log(k,v);
    });
    
    //es5遍历
    nums.forEach(function(item,index){
        console.log(item,index);
    });
```
------

### 数组转换
#### 需求：[将数值数组的元素进行二倍值返回]
```javascript
    //传统 es
    var res = [];
    for (var i = 0; i < nums.length; i++) {
        res.push(nums[i] * 2);
    }
    console.log(res);

    //jquery 数组转换
    var res = $.map(nums, function (item, index) {
        return item * 2;
    });
    console.log(res);
    
    //es5 数组转换
    var res = nums.map(function (item, index) {
        return item * 2;
    });
    console.log(res);


    //-------- 拓展说明 --------
    //$.map() 如果内部不进行return 值，则对应项不会出现在新数组中
    var res = $.map(nums, function (item, index) {
        if(item > 30){
            return item * 2;
        }
    });
    console.log(res); // [66, 88, 110]


    //es5 map() 如果内部不进行 return 值，或return false ,则该值均为 undefined
    var res = nums.map(function (item, index) {
        if(item > 30){
            return item * 2;
        }
    });
    console.log(res); //[undefined, undefined, 66, 88, 110, undefined]
```
------

### 数组过滤
#### 需求：[获取数组中数值大于 30 的元素]
```javascript
    //传统过滤
    var res =[];
    for(var i=0;i < nums.length; i++){
        if(nums[i] > 30){
            res.push(nums[i]);
        }
    }
    console.log(res);

    //jquery 过滤
    var res =$.grep(nums,function(item,index){
        return item > 30;
    });
    console.log(res);

    //es5 filter 过滤
    var res    =nums.filter(function(item){
        return item > 30;
    });
    console.log(res);
```
------

### 数组合并
#### 需求：[合并两个数组并输出]
```javascript
    //传统-合并 合并后返回新数组 
    var res =colors.concat(nums);
    console.log(res);       //返回新数组
    console.log(colors);    //colors 未改变

    //传统-原型合并
    Array.prototype.push.apply(arr1,arr2);

    //jquery合并 将数组合并到目标数组中
    var res =$.merge(colors,nums);
    console.log(res);       // res === colors
    console.log(colors);
```
------

### 数组去重

#### 需求：[去除数组中重复的元素]
```javascript
    //传统去重
    var tempOjb ={};
    var tempArr =[];
    for(var i=0;i < nums.length; i++){
        if( tempOjb[nums[i]] === undefined ){
            tempOjb[nums[i]] = null;
            tempArr.push(nums[i]);
        }
    }
    console.log(tempArr);

    //jquery去重 
    //说明:$.unique() 会直接对原数组进行更改
    $.unique(nums);
    console.log(nums);
    
    //es5去重
    var sets =new Set();
    nums.forEach(function(item){
        sets.add(item);
    });
    var res = Array.from(sets);
    console.log(res);
```

============================================================




<style>
    *{ font-family:微软雅黑; }
</style>