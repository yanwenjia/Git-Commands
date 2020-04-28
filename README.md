#### 基本使用,只需要以下四步
```
git add .
git commit -m <信息>
git pull
git push
```
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




命令|参数|说明
:-:|:-:|:-:
git clone -b <branch> url || 克隆指定分支
git add|`<file name>`|添加文件到暂存区
git commit|-m "<提交信息>"|暂存区的修改提交到分支
git commit --amend -m <信息>||使用新的提交代替上次提交
git pull|  |拉取远程数据
git push|  |将本地数据推送到远程
git push origin local-branch:origin-branch ||推送分支到远端（指定本地分支和远程分支）
git push origin --delete <branch> || 删除远程分支
ssh-keygen|| 生成SSH公钥 
git reset HEAD <文件> | | 取消单个文件的add
git reset HEAD | | 取消所有文件的add, 保留文件的更改
git reset --hard | | 取消所有文件的add, 不保留文件的更改
git stash save <信息>| | 暂存当前修改
git stash pop | | 弹出暂存的修改
git stash list | | 当前暂存列表
git stash clear | | 删除所有暂存
git stash drop stash @{index} | | 删除第index个暂存
git stash apply stash @{index} | | 应用第index个暂存
git reset --soft || 删除提交，已改内容放在暂存区
git reset --mixed || 删除提交，已改内容放在工作区
git reset --hard HEAD^ || 删除提交，彻底删除
git reset --hard <版本号> || 删除提交，彻底删除
git reset || 撤销还没有提交远程的更改
git revert || 撤销已经提交远程的更改
git revert -n <版本号> || 
git tag -a <版本> -m <信息> || 打tag
git tag -l -n || 列出所有tag及备注
git checkout <tag> || 切换到指定tag
git checkout -b branch <tag> ||创建指定tag的分支
git log || 查看日志
git branch <new-branch> ||创建新分支
git branch -d <branch> ||删除分支
git branch -b <new-branch> ||创建新分支并且切换到新分支
git merge <branch> || 合并分支到当前分支
git remote -v || 查看远程地址仓库
git remote rm origin ||删除关联的远程仓库
git remote add origin <url> || 添加远程仓库地址
git mv <old> <new> || 文件重命名
git rm <文件路径> -r || 删除文件夹


 