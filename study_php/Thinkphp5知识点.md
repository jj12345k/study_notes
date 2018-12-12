## 【多行字符串】
1. Heredoc :支持 变量解析
```php
<<< EOT
    <div class='ui_wbox'>
        <span>{$title}：</span>

        <div class="uploadArea">
            <img src="{$img_url}" alt="" id="upload_img" />
            <input type="hidden" name="{$pic_name}" value="{$url}">
            <p><input type="button" value="点击上传" id="btn_upload"></p>
        </div>
    </div>
EOT
```

2. Nowdoc :不支持 变量解析
```php
<<< 'EOT'
    <div class='ui_wbox'>
        <span>{$title}：</span>

        <div class="uploadArea">
            <img src="{$img_url}" alt="" id="upload_img" />
            <input type="hidden" name="{$pic_name}" value="{$url}">
            <p><input type="button" value="点击上传" id="btn_upload"></p>
        </div>
    </div>
EOT
```

## 【分页带参数】
说明：paginate(number:分页条数, bool:是否为简单分页, array:参数数组)
> Db:("goods")->paginate(15,false,["query"=>$search]);

## 【input() 用法注意事项】
input($key = '', $default = null, $filter = '')
> 参数说明 $key 为指定获取的字段，$default 为默认值，$filter 为过滤的方法

不可配置 原因：/ 反斜杠方式用作路由匹配
> input("get.name")  http://localhost/mall/index.php/admin/test/index/name/123

可以配置 input("get.name")
> input("get.name")  http://localhost/mall/index.php/admin/test/index?name=123

提交的是数组必须通过 /a 方式接收，否则报错
> input("attr_value/a")

input("session.account") input("cookie.account") 可以获取session 和 cookie，但是不建议这么使用

## 【Db 类的常规操作】

### insert部分
- **插入数据并返回对应主键:** insertGetId() 

### delete部分
- **删除单条数据:** delete(id) / where(id,1)->delete()
- **删除多条数据:** delete([1,2,3...]) / where('id','in',[1,2,3,4])->delete()


### update部分
注意：链式调用的自增、自减为 inc()、dec() 有别于 setInc() 和 setDec()
- **更新某个字段:** setField(string'字段名',type:'值') 
- **自增:** setInc(string:'字段名',number:'步长')
- **链式调用:** Db::table('data') ->where('id',1)->inc('read')->dec('score',3)->exp('name','UPPER(name)')->update();

### select部分
Db::table() 可以指定表前缀
Db::name()  无需指定表前缀

- **查找单条数据:** find()
- **查找多条数据:** select()
- **值查询:** value()
- **列查询:** column()

### where高级部分
查询表达式 where('字段名','表达式','查询条件')
> 表达式：>、<、=、<>、like、in、between、null、时间查询

聚合查询
> count() sum() max() min() avg

时间查询
> 具体见文档