### Git应用的常用场景

## 基本使用,只需要以下四步
```
git add .
git commit -m <信息>
git pull
git push
```



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


 