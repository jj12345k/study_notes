
## 注意事项
### 文字
> 1.只能放在 <Text> 标签中，否则会报错
> 2.文字居中必须要在 Text 标签中定义样式，不能在父级添加textAlign 是文字居中


## 样式区别
> width height 等长度属性不用带单位
> width height 等长度单位支持 ％ 写法
> border margin 等复合属性需要拆分成单属性
> 无 boxSizing 样式，模样 box-sizing 为 border-box
> 无 backgroundImage 样式，需要使用 <ImageBackground  source={require('url')}>
> overflow 样式有兼容性问题，不支持overflow-x/overflow-y

```javascript
{
    // 主轴对齐方式
    "justifyContent":{  
        "flex-start",
        "center",
        "flex-end",
        "space-around",
        "space-between",
        "space-evenly"
    }, 
    
    // 多轴对齐方式
    "alignItems": {
        "flex-start",
        "center",
        "flex-end",
        "stretch"
    },
    "alignContent", 
    "alignSelf",
    "aspectRatio",
    "backfaceVisibility",
    "backgroundColor",
    "borderBottomColor",
    "borderBottomEndRadius",
    "borderBottomLeftRadius",
    "borderBottomRightRadius",
    "borderBottomStartRadius",
    "borderBottomWidth",
    "borderColor",
    "borderEndColor",
    "borderEndWidth",
    "borderLeftColor",
    "borderLeftWidth",
    "borderRadius",
    "borderRightColor",
    "borderRightWidth",
    "borderStartColor",
    "borderStartWidth",
    "borderStyle",
    "borderTopColor",
    "borderTopEndRadius",
    "borderTopLeftRadius",
    "borderTopRightRadius",
    "borderTopStartRadius",
    "borderTopWidth",
    "borderWidth",
    "bottom",
    "color",
    "decomposedMatrix",
    "direction",
    "display",
    "elevation",
    "end",
    "flex",
    "flexBasis",
    "flexDirection",
    "flexGrow",
    "flexShrink",
    "flexWrap",
    "fontFamily",
    "fontSize",
    "fontStyle",
    "fontVariant",
    "fontWeight",
    "height",
    "includeFontPadding",
    "left",
    "letterSpacing",
    "lineHeight",
    "margin",
    "marginBottom",
    "marginEnd",
    "marginHorizontal",
    "marginLeft",
    "marginRight",
    "marginStart",
    "marginTop",
    "marginVertical",
    "maxHeight",
    "maxWidth",
    "minHeight",
    "minWidth",
    "opacity",
    "overflow",
    "overlayColor",
    "padding",
    "paddingBottom",
    "paddingEnd",
    "paddingHorizontal",
    "paddingLeft",
    "paddingRight",
    "paddingStart",
    "paddingTop",
    "paddingVertical",
    "position",
    "resizeMode",
    "right",
    "rotation",
    "scaleX",
    "scaleY",
    "shadowColor",
    "shadowOffset": {width: 0, height: 3},
    "shadowOpacity",
    "shadowRadius",
    "elevation": 4, // 使安卓阴影生效，不过颜色灰色不可改
    "start",
    "textAlign",
    "textAlignVertical",
    "textDecorationColor",
    "textDecorationLine",
    "textDecorationStyle",
    "textShadowColor",
    "textShadowOffset",
    "textShadowRadius",
    "tintColor",
    "top",
    "transform": [{scaleX: String}, {rotate: String}, ...]
    "transformMatrix",
    "translateX",
    "translateY",
    "width",
    "writingDirection",
    "zIndex"
}
```