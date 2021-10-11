# SHELL时间戳转换

```shell
date -d @1627374653 "+%Y-%m-%d-%H-%M-%S"
```

写到脚本里，方便使用：

```sh
##########################################################################
# File Name: timetran.sh
# Author: wh
# Created Time: Thu 30 Sep 2021 11:40:24 AM CST
#########################################################################
#!/bin/zsh
timestamp=$1
time=$(date -d @$timestamp "+%Y-%m-%d %H:%M:%S")
echo $time

```

调用：

```sh
bash timetran.sh 1627374653
```

# Mac时间戳转换

```shell
date -r '1627374653' ["+%Y-%m-%d %H:%M:%S"]
```

