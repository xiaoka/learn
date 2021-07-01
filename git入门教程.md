## git入门教程
> 生成公钥 ssh-keygen -t rsa -C "邮箱" (后面的直接回车就好)

> 首先克隆 git clone 项目地址

> 然后把项目 pull下来 git pull

> 创建分支 git checkout -b 分支名

> git checkout . #本地所有修改的。没有的提交的，都返回到原来的状态

> 查看状态 git status (如果有红色文件)

    —> git add .||"具体某个文件名"
    
    —> git reset （取消add）
    
    —> git status （文件变绿色）
    
    —> git commit -m "说明"
    
    —> git log 查看日志
    
> 提交到服务器

    —> git checkout master
    
    —> git pull (注意提交之前一定要pull)||git pull origin master

    —> git merge 分支名（合并分支）
    
    —> git push （提交）


> 创建分支 git checkout -b 分支名

> 查看所有分支 git branch

> 切换分支 git checkout 分支名

> 删除分支 git branch -d 分支名

> 修改分支名字 git branch -m  oldname newname

> 修改源 git remote set-url origin 源的地址

> 查看源地址 git remote -v

> 忽略文件 git update-index --assume-unchanged /path/file

> 恢复跟踪 git update-index --no-assume-unchanged /path/file 

> 拉去其他源文件

    —> git remote add 源的名 源的git路径

> 回滚

    -> git reflog 日志
    -> git reset --hard 日志号


> 暂存修改工作区 git stash  

> 将工作区还原并删除 git stash pop stash@{0}

> 查看工作区 git stash list
