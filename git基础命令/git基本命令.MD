# git常用命令

#### 1.git clone <版本库网址>
> 从远程主机克隆一个版本库，该命令将会在本地主机生成一个目录，与远程主机版本库同名。

#### 2.git init
> 在本地初始化一个版本库，默认会在当前文件夹下创建.git文件夹。

#### 3.git remote
> 为了便于管理，git要求每个远程主机都必须指定一个主机名。git remote命令就用于管理主机名。
- git remote
  - 不带选项时，git remote命令列出所有远程主机。
- git remote -v
  - 使用-v选项，查看远程主机的网址。
- git remote show <主机名>
  - 使用show命令，查看主机详细信息。
- git remote add <主机名> <网址>
  - add命令添加远程主机，其中主机名表示这个远程仓库名称。
- git remote rm <主机名>
  - rm命令用于删除远程主机。
- git remote rename <原主机名> <新主机名>
  - rename用于重命名主机。
#### 4.git log
> 在提交了若干更新之后，或者克隆某个项目后，想回顾提交历史，使用log命令查看。
- git log
  - 默认不用任何参数的话，git log按照提交时间列出所有更新，最近的排在最上面。
- git log -p -2
  - 使用-p选项展开显示每次提交的内容差异，使用-2则仅显示最近的两次更新。
- git log --stat
  - 使用stat表示显示简要的增改行数统计。
- git log --pretty=oneline
  - 用online将每个提交放在一行显示，这在提交数很大时非常有用。
- git log --pretty=format:"%h - %an, %ar : %s"
  - format方式可以定制要显示的记录格式，这样的输出便于后期编程提取分析。
> 更多关于git log的方法，参考：http://blog.csdn.net/wh_19910525/article/details/7468549
#### 5.git fetch
> 一旦远程主机版本库有了更新，需要将这些更新取回本地，使用fetch命令。
- git fetch <远程主机名>
  - 取回远程主机所有分支更新。
- git fetch <远程主机名> <分支名>
  - 指定分支名获取远程主机更新。
#### 6.git pull
> 取回远程主机某个分支的更新，再与本地的指定分支合并。
- git pull <远程主机名> <远程分支名>:<本地分支名>
  - 比如取回origin主机的next分支，与本地的master分支合并，需要这样写:git pull origin next:master
  - 如果远程分支与当前分支合并，则冒号后可以省略。