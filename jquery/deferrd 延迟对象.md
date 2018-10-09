# deferred 应用

[概念]：耗时操作既有异步的操作（比如ajax读取服务器数据），也有同步的操作（比如遍历一个大型数组），它们都不是立即能得到结果的，deferred对象的含义就是"延迟"到未来某个点再执行。deferred对象就是jQuery的回调函数解决方案；

[参考链接](https://www.cnblogs.com/147258llj/p/5689694.html)

## 传统 ajax 和 deferred 改写 ajax 

### 传统ajax操作
```javascript
    $.ajax({
        type    :"post",
        dataType:"json",
        url     :"http://192.168.11.113/api/index.php/admin/api/index",
        success :function(res){},
        error:function(){}
    });
```
### deferred 改写
> - deferred对象的另一大好处，就是它允许你为多个事件指定一个回调函数
> - done 相当于success 默认还会将 res 传递给下一个then
> - fail 相当于error
> - then 如何只传递一个参数，相当于done

```javascript
    //说明：$.ajax() 默认返回一个 deferred 延迟对象
    $.ajax({
        type    :"post",
        dataType:"json",
        url     :"http://192.168.11.113/api/index.php/admin/api/index",
    }).done(function(res){
        console.log(res);
    }).fail(function(){
        alert("错误啦~");
    });
```
###
------

## $.when() 为多个操作指定回调

```javascript
    $.when($.ajax({
        type    :"post",
        url     :"http://192.168.11.113/api/index.php/admin/api/index",
        dataType:"json"
    }),$.ajax({
        type    :"post",
        url     :"http://192.168.11.113/api/index.php/admin/api/index2",
        dataType:"json"
    })).done(function(res0,res1){ // res0 代表 jqxhr1, res1 代表jqxhr2
        console.log(res0,res1);
    });
```






























<style>
    *{ font-family:微软雅黑; }
</style>
