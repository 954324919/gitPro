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
#### 7.git push
> 该命令将本地分支的更新，推送到远程主机。
- git push <远程主机名> <本地分支名>:<远程分支名>
  - 如果省略远程分支名，表示将本地分支推送与之存在"追踪关系"的远程分支。
- git push origin --delete master
  - 上边命令表示删除origin主机的master分支。
- git push -u origin master
  - 如果当前分支与多个主机存在追踪关系，可以使用-u选项指定一个默认主机。
- git push --all origin
  - 将所有本地分支都推送到origin主机。
#### 8.git clean
> 使用该命令可以删除一些没有git add的文件
- git clean -n
  - 使用-n参数显示将要删除的文件和目录
- git clean -f <文件名>
  - 使用-f删除文件
- git clean -df <目录名>
  - 使用-df删除文件和目录

#### 常用命令整理，摘抄自:http://www.jianshu.com/p/a4eec05c7659
>1.Git常用命令
| 命令 | 简要说明 |
| -------- | -------- |
| git add | 添加至暂存区
 |
| git add–interactive | 交互式添加
 |
| git apply | 应用补丁 |

| git am | 应用邮件格式补丁
 |
| git annotate | 同义词，等同于 git blame
 |
| git archive | 文件归档打包
 |
| git bisect | 二分查找
 |
| git blame | 文件逐行追溯
 |
| git branch | 分支管理
 |
| git cat-file | 版本库对象研究工具
 |
| git checkout |检出到工作区、切换或创建分支
 |
| git cherry-pick | 提交拣选
 |
| git citool | 图形化提交，相当于 git gui 命令
 |
| git clean | 清除工作区未跟踪文件 |

| git clone | 克隆版本库 |

| git commit | 提交 |
| git config | 查询和修改配置
 |
| git describe | 通过里程碑直观地显示提交ID |
| git diff | 差异比较
 |
| git difftool | 调用图形化差异比较工具 |
| git fetch | 获取远程版本库的提交
 |
| git format-patch | 创建邮件格式的补丁文件。参见 git am 命令 |

| git grep | 文件内容搜索定位工具
 |
| git gui | 基于Tcl/Tk的图形化工具，侧重提交等操作
 |
| git help | 帮助
 |
| git init | 版本库初始化 |
| git init-db* | 同义词，等同于 git init |
| git log | 显示提交日志
 |
| git merge | 分支合并
 |
| git mergetool | 图形化冲突解决
 |
| git mv | 重命名
 |
| git pull | 拉回远程版本库的提交 |
| git push | 推送至远程版本库 |
| git reBase | 分支变基 |
| git rebase–interactive | 交互式分支变基
 |
| git reflog | 分支等引用变更记录管理 |
| git remote | 远程版本库管理 || git repo-config* | 同义词，等同于 git config |
| git reset | 重置改变分支“游标”指向 |
| git rev-parse | 将各种引用表示法转换为哈希值等 |
| git revert | 反转提交 |
| git rm | 删除文件 |
| git show | 显示各种类型的对象 |
| git stage* | 同义词，等同于 git add |
| git stash | 保存和恢复进度
 |
| git status | 显示工作区文件状态
 |
| git tag | 里程碑管理
 |

