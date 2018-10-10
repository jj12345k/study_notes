# Error 对象
## [概念]：
error，指程序中的非正常运行状态，在其他编程语言中称为“异常”或“错误”。解释器会为每个错误情形创建并抛出一个Error对象，其中包含错误的描述信息。

###  js中六大错误类型
> - ReferenceError:找不到对象时
> - TypeError:错误的使用了类型或对象的方法时
> - RangeError:使用内置对象的方法时，参数超范围
> - SyntaxError:语法写错了
> - EvalError:错误的使用了Eval   
> - URIError:URI错误

### 使用要点
> - 使用try包裹的代码，即使不出错，效率也比不用try包裹的代码低；
> - 在try中，尽量少的包含可能出错的代码；
> - 无法提前预知错误类型的错误，必须用try catch捕获；
> - finally可以省略；

```javascript
    try{
        可能发生错误的代码
    }catch(err){
        console.log(err.msg);
        只有发生错误时才执行的代码
    }finally{
        无论是否出错，肯定都要执行的代码
    }
```

### 抛出自定义错误
> throw new Error("提示文字")；

```javascript
    
    function test(num){
        if(num > 10){
            throw new Error("num 不能大于10!");
        }
    }

    try{
        test(11);
    }catch(err){
        console.log(err.message);
    }

```
------