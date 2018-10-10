# git 操作文档

## 基本配置
> git config --global user.name="吴荣"  
> git config --global user.email="2284820944@qq.com"

## 基本操作

### 文件增删改查
> git add [file1] [file2]       :: 增加
> git rm [file1] [file2]        :: 删除
> git status                    :: 查询变更信息
> git log                       :: 查询当前分支版本
> git show [hash]               :: 查看对应文件的变化

### 其它命令
> git remote -v                 ::查看远程仓库
> git remote add origin +url    ::配置当前连接的仓库
> git push orign master         ::将项目推送至远程仓库

### 一般流程
> git init
> git add .
> git status
> git commit -m "一些提交信息"
> git commit -a -m "一些提交信息"
> git remote add origin "http:://www.github.com/jj12345k/demo"
> git push origin master 

### 常规流程
> step:1 优先在github 上创建仓库
> step:2
> git clone "http:://www.github.com/jj12345k/demo"
> git commit -a -m "一些提交信息"
> git push origin master 