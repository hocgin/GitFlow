# Git 部分指令
```shell
git config --global user.name "<user-name>"
git config --global user.email <email>

git branch # 查看当前所有分支
git branch -d <branch-name> # 删除分支

git checkout <branch-name> # 切换分支／标签
git checkout -b <new-branch-name> # 创建并切换到新分支

git rm --cached <file-path> # 移除提交文件, 不删除物理文件
git rm --f <file-path> # 移除提交文件, 并删除物理文件

git log # 查看日志信息

git status # 用于查看提交状态

git describe # 显示描述信息

git show

git diff <file-name> # 用于查看与历史文件区别

git fetch # 从远程获取所有分支最新版本到本地，不会自动merge(合并)
git fetch origin <branch-name> # 从远程获取指定分支最新版本到本地，不会自动merge
git pull # 从远程获取所有分支最新版本到本地，自动merge(合并)
git pull origin <branch-name> # 从远程获取指定分支最新版本到本地，自动merge(合并)

git rebase <branch-name> # 将指定分支的代码合并到当前分支，并按照提交的顺序排序，不创建新的节点
git merge <branch-name> # 将指定分支的代码合并到当前分支，并创建新到节点

git push origin :<old-branch> # 删除已存在的分支

git tag # 在控制台打印出当前仓库的所有标签
  -l <exp-value> # 搜索匹配的标签名
  -d <tag-name> # 删除指定标签
  -m <marks> # 添加备注
```

# Q&A
[git merge 和 git rebase 到区别](http://blog.csdn.net/wh_19910525/article/details/7554489)
[Git Flow](http://www.jianshu.com/p/ca5ee4ea6420?hmsr=toutiao.io&utm_medium=toutiao.io&utm_source=toutiao.io)
