# js 异步编程/对比

**[案例一]**
> - 需求： jquery ajax 获取 A 接口数据，根据获取 A 接口 数据的state 状态判断是否继续获取 B 接口数据。
> - 接口格式 {state:1,msg:'',data:[]}

## 传统回调解决异步问题
传统多层嵌套回调导致代码逻辑不混乱、不清晰
```javascript
    $.ajax({
        type    : "post",
        url     : "http://192.168.11.113/api/index.php/admin/api/a",
        dataType: "json",
        success: function (res) {
            if(res.state == 1){]

                $.ajax({
                    type    : "post",
                    url     : "http://192.168.11.113/api/index.php/admin/api/b",
                    dataType: "json",
                    success: function (res) {
                        console.log(res);
                    }
                });

            }else{
                console.log(res.msg);
            }
        }
    })；
```

## jquery ajax 提供的异步方案

> 知识点说明
> jqAjax 执行后返回了一个deferred 对象，可以使用该对象实现异步回调方案
> - done 相当于 success 函数
> - fail 相当于 error 函数，出错后执行 

```javascript
    $.ajax({
        type    : "post",
        url     : "http://192.168.11.113/api/index.php/admin/api/a",
        dataType: "json",
    }).done(function(res){    

        if(res.state == 1){

            $.ajax({
                type    : "post",
                url     : "http://192.168.11.113/api/index.php/admin/api/b",
                dataType: "json",
                success :function(res){
                    console.log(res);
                },
                error   :function(){

                }
            });

        }else{
            throw new Error("错误啦~");
        }

    }).fail(function(){
        alert("发生错误啦~");
    });
```

## es6 Promiss
```javascript
    var ajax =function(){
            return new Promise(function(resolve,reject){
            $.ajax({
                type    : "post",
                url     : "http://192.168.11.113/api/index.php/admin/api/a",
                dataType: "json",
                success: function (res) {
                    if(res.state == 1){
                        resolve();
                    }else{
                        throw new Error("错误啦:"+res.msg);
                    }
                }
            })
        });
    }

    ajax().then(function(){
        
        $.ajax({
            type    : "post",
            url     : "http://192.168.11.113/api/index.php/admin/api/b",
            dataType: "json",
            success: function (res) {
                console.log(res);
            }
        });

    }).catch(function(){
        console.log("错误啦~");
    });
```
------

**[案例二]**
> - 需求： 异步加载3张图片，只有当 3 张图片加载完毕后才显示图片，如果其中一张图片加载失败，则不显示图片

### jquery deferred 实现异步方式 

```javascript
    var loadImage = function(url){
        var defer =$.Deferred();

        var image   =new Image();
        image.src   =url;

        image.onload    =function(){
            defer.resolve(image);
        }

        image.onerror   =function(e){
            throw new Error("图片加载失败~");
        }

        return defer.promise();
    }
    
    $.when(
        loadImage("images/news_1.jpg"),
        loadImage("images/news_2.jpg"),
        loadImage("images/news_3.jpg")
    ).done(function(res1,res2,res3){
        console.log(res1);
        console.log(res2);
        console.log(res3);

        $(".box").append(res1);
        $(".box").append(res2);
        $(".box").append(res3);

    }).fail(function(){
        console.log("图片加载出错~");
    });
```

### es6 Promise 方案
```javascript
    var loadImage   =function(url){
        return new Promise(function(resolve,reject){
            var image   =new Image();
            image.src   =url;

            image.onload    =function(){
                resolve(image);
            }

            image.onerror   =function(e){
                throw new Error("图片加载失败~");
            }
        });
    }

    Promise.all([
        loadImage("images/news_1.jpg"),
        loadImage("images/news_2.jpg"),
        loadImage("images/news_3.jpg"),
    ]).then(function(img){
        $(".box").append(img);
    });

    
```


<style>
    *{ font-family:微软雅黑; }
</style>
