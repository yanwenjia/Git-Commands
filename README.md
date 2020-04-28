#### 基本使用,只需要以下四步
```
git add .
git commit -m <信息>
git pull
git push
```
#### 生成密匙
- `ssh-keygen -t rsa -C "<email>"`
#### 克隆操作
- `git clone <url>` 克隆远程仓库 
- `git clone -b <url>` 克隆远程仓库-指定分支
#### 配置操作
- `git config --list ` 查看配置列表
- `git config --global --list ` 查看全局配置列表
- `git config --global user.name <name>` 配置用户名
- `git config --global user.email <email>` 配置邮箱
#### 分支操作
- `git branch <new-branch>`  创建新分支
- `git checkout <branch>`  切换分支
- `git check -b <new-branch>`  创建新分支并切换到新分支
- `git branch -d <branch>`  删除分支
- `git push origin <local-branch>:<local-branch>`  将本地分支推送到远程仓库
- `git push origin --delete <branch>`  删除远程分支
- `git branch <new-branch> <tag>`  以指定tag创建分支
- `git checkout -b branch <tag>`  以指定tag创建分支并切换到创建的分支
- `git merge <branch>`  合并指定分支到当前分支
#### tag操作
- `git tag <tag>`  创建新标签-轻量标签
- `git tag -a <tag> -m <注释>`  创建新标签-附注标签
- `git tag`  查看标签列表
- `git tag -l -n`  查看标签列表-带注释信息
- `git push origin --tags`  将标签信息推送到远程仓库
#### 暂存操作
- `git stash` 暂存当前工作区的更改
- `git stash save <备注>` 暂存当前工作区的更改并添加备注信息
- `git stash pop` 应用最新的stash并删除他
- `git stash clear` 删除所有暂存
- `git stash list`  查看所有暂存
- `git stash apply <index>` 应用指定下标index的暂存,下标通过`git stash list`查看,例如stash@{0},下标为0
- `git stash drop <index>` 删除指定下标index的暂存,下标通过`git stash list`查看,例如stash@{0},下标为0
#### remote操作
- `git remote add origin <url>` 添加远程地址
- `git remote rm origin` 删除远程地址
- `git remote origin get-url` 获取远程地址
- `git remote origin set-url` 更改远程地址
#### 重命名
- `git mv <old> <new>` 重命名
#### 删除
- `git rm <文件路径> -r` 删除文件 -r(递归删除)
#### 合并commit
- `git commit --amend -m <信息>` 此次提交信息会和上次提交合并为一条提交信息
#### 版本回退
+ 工作区更改,尚未add
    + `git checkout .` 将取消工作区所有更改
+ 已经add,尚未commit
    + `git reset HEAD` 将取消所有add
+ 已经commit,尚未push
    + `git reset --mixed HEAD~1` 将取消上一次commit，更改内容放在工作区
    + `git reset --soft HEAD~1` 将取消上一次commit，更改内容放在暂存区
    + `git reset --hard HEAD~1` 将取消上一次commit，不保留更改内容
+ 已经push到远程仓库
    + 使用`git reset`
        1. `git log` 找到commitID
        2. `git reset --soft <commitID>` 恢复到指定commitID
        3. `git push -f` 强制提交远程仓库，必须加-f参数
    + 使用`git revert`
        1. `git log` 找到commitID(这个commitID比较特殊，找到提交信息之后，commitID并不是当条信息对应的commitID，而是他的后一次提交的commitID)
        2. `git revert -n <commitID>` 恢复到指定commitID
        3. `git push` 提交到远程仓库


 