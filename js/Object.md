# Object 专题篇

## 如何判断 对象是否为空
```javascript
    var demo ={};

    // 传统方式
    function checkObjIsNull(obj){
        if(typeof obj == "objeck") throw new Error("传入的不是一个对象！");
        for(var key in obj){
            if(key){
                return false;
            }
        }
        return true;
    }

    //jquery 方式
    $.isEmptyObject(demo);

    //es6 方式
    Object.keys(box).length

```