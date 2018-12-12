## 【htmlspecialchars 和 htmlspecialchars_decode】
htmlspecialchars 将特殊字符转换为 HTML 实体
htmlspecialchars_decode 将特殊字符转换为 HTML 普通字符

转换的字符如下：
``` php
& (& 符号) &amp; 
" (双引号) &quot;
' (单引号) &apos;
< (小于号) &lt; 
> (大于号) &gt; 
```

## 【htmlentities 和 html_entity_decode】
用法基本同上，区别[htmlentities会格式化中文字符使得中文输入是乱码 可能？]
htmlentities — 将字符转换为 HTML 转义字符
html_entity_decode】 将特殊字符转换为 HTML 普通字符

## 【explode、】
explode 用指定 字符模式 去分割字符串，返回数组[注意返回的类型时 字符型]
implode 用指定 字符模式 去拼接数组项，返回字符串

##