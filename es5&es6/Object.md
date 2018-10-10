# Object 对象专题

## Object.defineProperty(obj,props)
### pros 可选参数
> - configurable 是否允许该属性能够被删除 默认：false
> - enumerable 是否可枚举 默认：false
> - value 与属性关联的值 默认：undefined [可与writable 搭配，不可与set get 连用]
> - writable 是否可写(是否可重新赋值) 默认：false [value 搭配，不可与set get 连用]
> - get 作为该属性的 getter 函数，如果没有 getter 则为undefined。函数返回值将被用作属性的值。默认为 undefined
> - 作为属性的 setter 函数，如果没有 setter 则为undefined。函数将仅接受参数赋值给该属性的新值。默认为 undefined

```javascript
    var obj ={};

    Object.defineProperty(obj,"uname",{
        configurable    :true,  //可删除
        enumerable      : true, //可枚举
        set(val){       
            this._uname = `[${val}]`;
        },
        get(){
            return this._uname;
        }

        /*
            以下属性不能与 set 和 get 连用
            value   :"jack",    
            writable:true
        */

    });
```

