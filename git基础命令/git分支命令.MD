# git分支常用命令

#### git插件 oh-my-zsh，强大的bash工具。

#### git branch
> 对git分支的各种操作。
- git branch 
  - 列出本地已经存在的分支，并且在当前分支的前面加"*"号标记。
- git branch -r
  - 列出远程分支。
- git branch -a
  - 列出本地及远程分支。
- git branch <分支名>
  - 创建一个新的本地分支，需要注意，此处只是创建分支，不进行分支切换。
- git branch -m | -M <旧分支名> <新分支名>
  - 重命名分支，如果新分支名已经存在，需要使用-M强制重命名，否则，使用-m进行重命名。
- git branch -d | -D <分支名>
  - 删除分支
- git branch -d -r <分支名>
  - 删除远程分支
- git help branch
  - 查看分支的帮助信息

#### git checkout
> 切换分支，分支操作。
- git checkout <分支名>
  - 最常用的切换工作分支命令，该命令会切换当前的分支。
- git checkout -b <分支名>
  - 使用该命令会创建新分支，并且同时切换分支。



