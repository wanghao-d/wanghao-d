# git submodule

### 两种方式：

1. 
   ```shell
   $ git clone gitrepo
   $ git submodule init
   $ git submodule update
   ```

2. 给 git clone 命令传递 --recurse-submodules 选项，它就会自动初始化并更新仓库中的每一个子模块， 包括可能存在的嵌套子模块。
   ```shell
   $ git clone --recurse-submodules gitrepo
   ```

### submodule管理：

添加子模块：

```shell
git submodule add <url> <path>
# url为子模块仓库的路径，path为在代码中存放的位置。
```

删除子模块：

```shell
1. rm -rf dir/xxx 删除子模块目录及源码
2. vi .gitmodules 删除.gitmodules文件中子模块配置
3. vi .git/config 删除配置项中子模块配置
4. rm .git/module/xxx 删除.git中的子模块目录
5. git rm --cached xxx
```

