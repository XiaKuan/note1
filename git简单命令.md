`pwd `显示当前目录

`mkdir *** `创建空目录、

`ls -ah` 看隐藏目录

`git init`命令把这个目录变成Git可以管理的仓库

`git add ***.txt` 提交文件到仓库

```git
git commit -m "wrote a readme file"
git commit # 表示提交文件到仓库
-m 表示本次提交的说明
```

```
git status
查看仓库当前状态
git diff
查看具体修改了什么内容
```

```
git log 查看提交修改日志
git log --pretty=oneline 修改日志美化
HEAD 表示当前版本 前方字符表示版本
```

![image-20210224172831779](C:\Users\Xia Kuan\AppData\Roaming\Typora\typora-user-images\image-20210224172831779.png)

```
 git reset --hard HEAD^ 回退版本
 git reset --hard 0005 回到版本号0005开头
 cat readme.txt 查看文档内容
 git reflog 查看所有版本修改日志
 git checkout -- file 丢弃工作区的修改
```

```
git diff HEAD -- readme.txt
查看工作区和版本库最新版本的区别
```

```
rm test.txt 删除文件

```

```
git remote add origin git@github.com:michaelliao/learngit.git
连接本地库到远程仓库

git push origin main 把本地库的内容推送给到远程origin分支main

git clone git@github.com:michaelliao/gitskills.git
克隆到本地库
```



# 创建分支

```
git checkout -b dev
创建dev分支 ‘-b’表示创建并切换

```

```

git branch
查看当前分支
git branch <name>
创建分支
git branch -d dev
删除dev分支


git branch -D dev # 强制删除dev分支 强制删除未保存的内容和工作区分支
```

```
git switch -c dev
创建并切换到新的dev 分支
git switch main 切换到分支main
```

```
git merge dev
合并指定分支到当前分支
git log --graph --pretty=oneline --abbrev-commit
查看分支的合并情况
```

如果两个分支存在冲突会合并失败，许哟啊使用`git status`查看冲突的地方，需要手动解决冲突后再重新提交，合并之后可以在工作区文件看见

```
git merge --no-ff -m "merge with no-ff" dev
表示禁用Fast forward,创建日志历史
```

```
git stash 保存工作区
git stash list 临时保存的工作区列表
git stash pop 回复工作区
git cherry-pick <commit> 提交修改复制到分支
```

强制删除未保存的内容和工作区分支

`git branch -D dev`强制删除dev分支

```
git remote 查看远程库的信息
git remote -v 显示详细信息
git push origin main 推送main分支到远程库

git clone git@github.com:michaelliao/gitskills.git 只会克隆默认主分支
git checkout - b dev origin/dev 创建远程origin的dev分支到本地

如果多人提交冲突，可以使用
git pull 将最新的提交从origin/dev上抓取下来，在本地进行合并
git branch --set-upstream-to=origin/dev dev   设置dev和origin/dev的链接
再手动解决冲突
```

# 标签管理

```
git tag v1.0 打上标签
git tag 查看所有标签
git tag v0.9 f52c633 给对应的commit打上tag
git tag -a v0.1 -m "version 0.1 released" 1094adb 创建带有说明的标签，-a指定标签名，-m指定说明文字
git show v0.1 可以看到说明文字

git tag -d v0.1 删除标签
git push origin v1.0 推送某个标签到远程
git push origin --tags 一次性推送所有未推送到远程的本地标签
git push origin :refs/tags/v0.9 删除远程标签
```



# 