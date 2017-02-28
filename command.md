```shell
# 初始化 Git 仓库
git init
# 加入提交文件
git add README.md
# 加入备注信息
git commit -m "v0.1.0 初始化版本"
# 指定提交仓库, GitHub 提前建库
git remote add origin https://github.com/hocgin/GitFlow.git
# 提交
git push -u origin master

# 创建 develop 分支
git checkout -b develop
git push --set-upstream origin develop
# 创建 feature-n0001 分支
git checkout -b feature-n0001
git push --set-upstream origin feature-n0001

# 修改 README.md 后
git add README.md
git commit -m "feature 进行功能开发"
git push --set-upstream origin feature-n0001
# 再次修改 README.md 后
git add README.md
git commit -m "feature 研发进度更新"
git push --set-upstream origin feature-n0001

# 切换到 develop, 修改 README.md 后
git checkout develop
git add README.md
git commit -m "更新 develop"
git push origin develop

# 【feature-n0001 分支的开发成员】, 把 develop 的变更合入 feature-n0001
git fetch origin # 远程库的更新全部取回本地库
git rebase feature-n0001  # 把 feature-n0001 分支的子分支 修改合并到 feature-n0001 分支
git push origin feature-n0001

# 【feature-n0001 的管理者】，把feature-n0001 分支的子分支合并后，再合并到 develop分支，然后并重建 feature-n0001 分支
git fetch origin
git rebase feature-n0001
git rebase develop
git push origin :feature-n0001 # 删除 feature-n0001 分支
git push origin feature-n0001 # 重建 feature-n0001 分支

# 【feature-n0001 分支的开发成员】开发完成后,提交所有 feature-n0001分支 的代码
git fetch origin
git rebase origin/feature-n0001
git push origin feature-n0001

# 【feature-n0001 的管理者】，合并 feature-n0001分支 的代码，并删除 feature-n0001分支
git fetch origin
git rebase origin/feature-n0001
git rebase develop
git checkout develop
git merge feature-n0001
git push origin :feature-n0001

# 【feature-n0001 的管理者】，拉出对应的 release/feature-n0001分支，后续bug修复在release/feature上
git checkout develop
git checkout -b release-n0001

# bug修复完成后，拉取对应的tag推送远程进行发布
git tag -a v1.0.0 -m 'feature-n0001发布'
git push origin v1.0.0

# 将 release-n0001分支 合入develop分支, 删除
git rebase develop
git checkout develop
git merge release-n0001
git push origin :release-n0001

```
