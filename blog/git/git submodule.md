# git submodule

两种方式：

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