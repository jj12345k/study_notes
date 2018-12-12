# Git 进阶


## git 基本操作
> git init 
> git add file/.
> git commit file -m "注释"
> git remove add origin https://_url
> git push -u origin master

## 为当前工作区目录添加远程仓库
> git remote add origin http://github.com/jj12345k/study_test   #添加远程链接
> git push orign master #将master主分支推送到 origin 源

## 如何删除 git 仓库
> 用户登陆后点击要删除的 仓库 -> setting -> 下来至底部 -> 点击删除 

## .gitignore 作用
> 作用：忽略.gitignore 中配置的文件 提交
> 用法：每一行表示一项需要忽略的文件/夹  
> 注释：#号开头  
> 例子：.vscode / node_module / *.js   
> 可以使用现成的模板

说明：  
.gitignore 中的配置项无法通过`git add +指定文件`添加到暂存区中，如果需要强制添加可以使用 `git add -f +指定文件方式添加`

## .gitignore 检测忽略了那些规则
> git check-ignore -v .node_module

## 回撤指令
> git reset / git reset HEAD~2

## git tag 操作用于给提交的版本打标志，可以用于重要历史版本的回撤和查看
> git tag name -m "注释"
> git tag 查看标志信息
> git tag -d 'name' 删除版本

## 配置 git 字符编号，使其支持 中文
![](img/gitconfig.gif "配置支付编码")

##显示配置信息
> git config --list

## 配置操作系统换行符 不提示
`git config --global core.safecrlf false`

## 基本配置
> git config --global user.name="吴荣"  
> git config --global user.email="2284820944@qq.com"

## git别名
> 方式一：直接通过命令行添加
> git config --global alias.名字 命令

> 方式二：通过编辑配置文件添加
> cd ~ 回退到用户家目录，.gitconfig 的存放位置
> vim .gitconfig
> ci - commit
> ad - add 
> br - branch

技巧：git log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short

## git 凭证管理
> git config --global credential.helper wincred

## git blame 审查文件修改信息
> git blame demo.txt 可以查看文件的变动信息
> git blame -L 5,10 demo.txt 查看5-10行信息的变动

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

## git 分支操作
> git branch 查看所有分支
> git branch +名称  分支创建
> git checkout +名称 切换分支
> git branch -d +名称 删除分支
> git merge + 名称 将指定分支合并到当前分支

> git branch -m old_name new_name
> git branch -r 列出远程的分支
> git branch -v 详细信息
> git branch --merged 查看已经合并的分支
> git branch --no-merged  查看没有合并的分支
> git checkout -t origin/foo 去除远程的分支

> git push origin +分支名
> git fetch -p 

# 疑难杂症
## push 推送 冲突解决
> git pull --rebase

## 更改远程的仓库地址：
场景：需要下载指定仓库的目录作为项目结构，然后向现有项目提交到新的远程仓库中托管
git remote rm origin
git remote add origin [url]


## 案例
### 案例一：
说明： 从 https://github.com/jj12345k/Vue_self_template 仓库中下载模板，然后重命名为 vue_shop 项目，最后提交到 远程 vue_shop中

### 案例二：

需求：
> 1.创建 self_tmpl 仓库  
> 2.将远程 self_tmpl 克隆到本地  
> 3.在本地创建 tmpl_pc、tmpl_wap、tmpl_rsp 分支  
> 4.分别向各分支添加对应模板，然后将对应模板提交至本地仓库托管  
> 5.将本地分支推送至远程仓库  
> 6.将远程对应的 tmpl_pc 分支下载到本地  

题解：  
步骤一：
> github 创建对应的 self_tmpl 仓库  

步骤二：
> git clone https://github.com/jj12345k/self_tmpl

步骤三、四：  
有用命令：
> git branch -v             #查看当前仓库拥有的分支
> git branch -d + 分支名     #删除对应的分支

> git branch tmpl_pc        #创建 tmpl_pc 分支  
> git checkout tmpl_pc      #切换至 tmpl_pc 分支  
> 向对应分支添加模块
> git add .                 #向暂存区中添加文件
> git commit -m '备注'      #提交至本地仓库

步骤五：
> git push origin tmpl_pc   #向远程提交 tmpl_pc分支
> git push origin tmpl_wap  #向远程提交 tmpl_wap
> git push origin tmpl_rsp  #向远程提交 tmpl_rsp

步骤六：
> git clone -b tmpl_pc https://github.com/jj12345k/self_tmpl #下载对应分支到本地





