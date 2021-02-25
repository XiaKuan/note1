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
git merge dev
合并指定分支到当前分支

git branch
查看当前分支
git branch <name>
创建分支
git branch -d dev
删除dev分支
```

```
git switch -c dev
创建并切换到新的dev 分支
git switch main 切换到分支main
```

