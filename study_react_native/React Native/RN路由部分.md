##基本步骤 
1. 优先安装 react-navigation [建议安装2.0.0版本]
> cnpm install react-navigation@2.0.0 --save

2. Src 下创建 RouterApp.js 页面用于路由管理

3. 在 RouterApp 中引入需要路由管理的组件/页面，并按如下进行处理

静态配置
```javascript
    // RouterApp.js 中的代码
    import { StackNavigator } from "react-navigation";

    // 引入组件
    import Login from "./views/Login";
    import Index from "./views/Index";

    export default StackNavigator(
        {
            Index   :{
                screen: Index,
            },

            Login   :{
                screen  :Login
                
                //【第二种配置方式 局部配置】
                navigationOptions :{    
                    //header :null          //去掉导航状态栏
                    title   :"登陆页面"      //导航标题
                }
            }
        },

        //【第一种配置方式 全局配置】
        {   
            navigationOptions :{
                //header :null      //全局去掉header
            }
        }

    )
    /************************************/

    // Index.js 代码 页面跳转到登陆页面

    //【第三种配置方式 页面局部】
    static navigationOptions ={
        header :null            //去掉导航状态栏
        title   :"登陆页面"      //导航标题
        headerRight: (),        //右侧按钮
        headerBackTitle:        //返回按钮文字
    }

    render() {
        const {navigation} = this.props;

        return (
            <TouchableOpacity onPress={()=>{navigation.navigate("Login")}}>
                <Text>前往页面通过 navigation.navigate("Login") </Text>
            </TouchableOpacity>

            <TouchableOpacity onPress={()=>{navigation.goBack()}}>
                <Text>会退至上一页</Text>
            </TouchableOpacity>
        );
    }
```

动态配置：
```javascript
    // RouterApp.js 中的代码
    import { StackNavigator } from "react-navigation";

    // 引入组件
    ... ...
    import Login from "./views/Login";
    
    export default StackNavigator(
        {
            Login   :{
                screen  :Login
                
                //方式一
                navigationOptions :(
                    ({navigation}) => ({    
                        title   : navigation.state.params.name
                    })
                )

                //方式二
                navigationOptions: (props)  =>{
                    const {navigation}      =props;
                    const {state,setParams} =navigation;

                    return {
                        title :state.params.title?state.params.title:""
                    };
                }
            }
        },
    )
    /***********************************************/

    //index.js 中的代码
    <TouchableOpacity onPress={()=>{navigation.navigate("Login",{name:"我是登陆页面"})}}>
        <Text>会退至上一页</Text>
    </TouchableOpacity>


```


