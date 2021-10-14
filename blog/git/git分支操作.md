# Git分支

### git 分支基本操作

```shell
# 创建新分支
git branch dev
# 将工作区恢复到上次提交的内容，同时备份本地所做的修改
git stash

# 切换分支
git checkout dev

# 从 git 栈中获取到最近一次 stash 的内容，之后会删除栈中对应的 stash
git stash pop
```

git clone分支

```shell
git clone -b dev_xx repo_url
```

### git 分支提交操作

```shell
# 添加所有（已修改）文件
git add .

# 添加到本地仓库，Win 注释用双引号
git commit -am "first commit init project"

# 获取
git pull origin 远程名称

# 推送
git push origin 远程名称
```

