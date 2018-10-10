# Function 函数篇

## return 和 return false
### 函数中 return 和 return false 的区别
知识点：
> return 和 return false/true 都能起到终止函数向下执行的效果，将控制权交还给调用的父级
> return 只起到单纯的终止函数执行的作用 无返回值(undefined)
> return false/true 表示返回函数执行的结果


### 函数中 for 循环 中的 return 、 break 、continue
知识点：
> return 直接跳出循环(单、嵌套循环)均会跳出，直接将结果进行返回。
> break 会跳出当前循环
> continue 会跳过当次循环中未执行的语句，执行下次循环

代码：
```javascript
    // 遇到 return 函数直接结束，返回值为 2
    function test(){
        for(var i=0; i<3; i++){

            console.log("外层：",i);
            for(var k=0; k<4; k++){
                if(k == 2){
                    return k;
                }
                console.log("内层：",k);
            }

        }
    }

    // 遇到 break 跳出【内层】循环，继续外层循环
    function test(){
        for(var i=0; i<3; i++){

            console.log("外层：",i);
            for(var k=0; k<4; k++){
                if(k == 2){
                    break;
                }
                console.log("内层：",k);
            }

        }
    }

    // 遇到 continue 结束【当次】循环，继续下次循环
    function test(){
        for(var i=0; i<3; i++){

            console.log("外层：",i);
            for(var k=0; k<4; k++){
                if(k == 2){
                    continue;
                }
                console.log("内层：",k);
            }

        }
    }
```
------

<style>
    *{ font-family:微软雅黑; }
</style>