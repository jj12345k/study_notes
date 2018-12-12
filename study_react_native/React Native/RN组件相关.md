#

## 【样式部分】
### 样式创建
```javascript
    const styles = StyleSheet.create({
        
    });
```

## 【Text 组件】
> onPress           事件
> numberOfLines     行数

## 【TouchableOpacity】
> TouchableOpacity      透明触摸
> TouchableHightlight   高亮触摸
> TouchableWithoutFeeback 无反馈触摸

## 【引用字体图标方式】
以下案例以 阿里IconFont 为例子

IOS配置：
> 1.在 xcode 中将iconfont 直接拖入 app\Images.xcassets
> 2.在 info.plist 中添加 Fonts provider for application 
> 3.在上一步基础上添加 iconfont.ttf
> 4.在需要用到字体图标的地方引入即可  <Text style={{fontFamily:'iconfont',fontSize:40}}>&#xe601;</Text>

安卓配置：
> 1. 将下载好的 iconfont.ttf 放入以下路径 app\android\app\src\main\assets\fonts
> 2. 在需要用到字体图标的地方引入即可  <Text style={{fontFamily:'iconfont',fontSize:40}}>&#xe601;</Text>


## 【引入图片的几种方式】
1.引用本地图片
`<Image source={require("../img/icon.png")} />`

2.引用网络图片
`<Image source={{uri:"http//..."}} />`

3.引用原生资源图片
说明:tintColor:可以指定png图片的颜色

苹果下引用配置
- 开打工程目录，找到 app\Images.xcassets 下直接将图片拖住进入窗口自动生成资源目录
- 2.代码如下：<Image source={{uri:"icon_guide"}} style={{width:50,height:50,tintColor:"blue"}} />

安卓下引用配置
- 1.在 app\android\app\src\main\res 路径下创建以 drawable-开头的文件夹用于存放自定义图片
- 2.代码如下：<Image source={{uri:"icon_guide"}} style={{width:50,height:50,tintColor:"blue"}} />
-------

