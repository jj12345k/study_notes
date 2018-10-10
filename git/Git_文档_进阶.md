# Git 进阶

## .gitignore 作用
> 作用：忽略.gitignore 中配置的文件 提交
> 用法：每一行表示一项需要忽略的文件/夹  
> 注释：#号开头  
> 例子：.vscode / node_module / *.js   
> 可以使用现成的模板

说明：  
.gitignore 中的配置项无法通过`git add +指定文件`添加到暂存区中，如果需要强制添加可以使用 `git add -f +指定文件方式添加`

## 配置操作系统换行符
`git config --global core.safecrlt false`

## 

## git别名
> 方式一：直接通过命令行添加
> git config --global alias.名字 commit
> 方式二：通过编辑配置文件添加
> cd ~ 回退到用户家目录，.gitconfig 的存放位置
> vim .gitconfig
> ci - commit
> ad - add 
> br - branch

## git 其它命令
> git 查看常用的命令
> git help -a 查看所有命令
> git blame <file> 查看文件的修改信息
> git blame -L 100,10 <file>
> git cleam -n 列出要清除的文件档案
> git clean -f 删除档案
> git clean -x -f 强制删除.gitignore 中的文件

> git rm <file> 和 rm 删除文件区别, git rm 删除后提交指暂存区，而 rm 删除后需要 git add . 才能提交至暂存区 

## git 查看信息
> git status -sb 以简短的信息显示文件状态信息
> git show HEAD 查看提交最后版本信息
> git show HEAD~1 查看最后一次提交的前一个版本信息
> git log 查看仓库的提交历史
> git log <file> 查看文件的提交历史
> git log --grep add 查看带有关键词的信息

## git add 命令
> git add . 将文件添加到暂存区
> git add <file> 添加到展存区

## git commit 命令
> git commit -am 跳过暂存区将数据提交至仓库

### git commit 个人规范

[阮一峰老师推荐规范_URL](http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html)

提交信息建议包括：
> 操作[范围]：主题
> type[scope]:subject
> - type    由动词和类型构成，动词不能省略
> - scope   可以省略
> - subject 主题 必须有动词开头，比如修改、修复、添加、编辑、删除等

> type 说明：
> - **操作动词**
> - new     新添加文件      [新建文件]
> - fix     修改bug        
> - feat    添加新特性
> - edit    常规编辑        [比如调整文件]
> - **文件类型**
> - html    html文件
> - style   样式文件
> - script  脚本文件
> - test    单元测试
> - docs    文档类型
> - notes   笔记类型

> **例子**
> new html[self_info.html]: 新建 个人信息.html
> edit css[common.css]： 修改 common 样式
> fix script [fns.js]：修改 htmlDecode() 函数
> fix [index.html & index.css]：修改 文本溢出后换行问题
> edit docs[git/git_文档_入门.md]：修改 补充部分知识点
> edit notes[git/git_文档_入门.md]：修改 个人笔记


<style>
    *{ font-family:微软雅黑; }
</style>