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
> 1.Git常用命令

| 命令 | 简要说明 |
| -------- | -------- |
| git add | 添加至暂存区 |
| git add–interactive | 交互式添加 |
| git apply | 应用补丁 |
| git am | 应用邮件格式补丁 |
| git annotate | 同义词，等同于 git blame |
| git archive | 文件归档打包 |
| git bisect | 二分查找 |
| git blame | 文件逐行追溯 |
| git branch | 分支管理 |
| git cat-file | 版本库对象研究工具 |
| git checkout |检出到工作区、切换或创建分支 |
| git cherry-pick | 提交拣选 |
| git citool | 图形化提交，相当于 git gui 命令 |
| git clean | 清除工作区未跟踪文件 |
| git clone | 克隆版本库 |
| git commit | 提交 |
| git config | 查询和修改配置 |
| git describe | 通过里程碑直观地显示提交ID |
| git diff | 差异比较 |
| git difftool | 调用图形化差异比较工具 |
| git fetch | 获取远程版本库的提交 |
| git format-patch | 创建邮件格式的补丁文件。参见 git am 命令 |
| git grep | 文件内容搜索定位工具 |
| git gui | 基于Tcl/Tk的图形化工具，侧重提交等操作 |
| git help | 帮助 |
| git init | 版本库初始化 |
| git init-db* | 同义词，等同于 git init |
| git log | 显示提交日志 |
| git merge | 分支合并 |
| git mergetool | 图形化冲突解决 |
| git mv | 重命名 |
| git pull | 拉回远程版本库的提交 |
| git push | 推送至远程版本库 |
| git reBase | 分支变基 |
| git rebase–interactive | 交互式分支变基 |
| git reflog | 分支等引用变更记录管理 |
| git remote | 远程版本库管理 || git repo-config* | 同义词，等同于 git config |
| git reset | 重置改变分支“游标”指向 |
| git rev-parse | 将各种引用表示法转换为哈希值等 |
| git revert | 反转提交 |
| git rm | 删除文件 |
| git show | 显示各种类型的对象 |
| git stage* | 同义词，等同于 git add |
| git stash | 保存和恢复进度 |
| git status | 显示工作区文件状态 |
| git tag | 里程碑管理 |

> 2.对象库操作相关命令
| 命令 | 简要说明 |
| -------- | -------- |
| git commit-tree | 从树对象创建提交 |
| git hash-object | 从标准输入或文件计算哈希值或创建对象 |
| git ls-files | 显示工作区和暂存区文件 |
| git ls-tree | 显示树对象包含的文件 |
| git mktag | 读取标准输入创建一个里程碑对象 |
| git mktree | 读取标准输入创建一个树对象 |
| git read-tree | 读取树对象到暂存区 |
| git update-index | 工作区内容注册到暂存区及暂存区管理 |
| git unpack-file | 创建临时文件包含指定 blob 的内容 |
| git write-tree | 从暂存区创建一个树对象 |

> 3.引用操作相关命令

| 命令 | 简要说明 |
| -------- | -------- |
| git check-ref-format | 检查引用名称是否符合规范 |
| git for-each-ref | 引用迭代器，用于shell编程 |
| git ls-remote | 显示远程版本库的引用 |
| git name-rev  | 将提交ID显示为友好名称 |
| git peek-remote* | 过时命令，请使用 git ls-remote |
| git rev-list | 显示版本范围 |
| git show-branch | 显示分支列表及拓扑关系 |
| git show-ref | 显示本地引用 |
| git symbolic-ref | 显示或者设置符号引用 |
| git update-ref | 更新引用的指向 |
| git verify-tag | 校验 GPG 签名的Tag |

> 4.版本库管理相关命令
| 命令 | 简要说明 |
| -------- | -------- |
| git count-objects | 显示松散对象的数量和磁盘占用 |
| git filter-branch | 版本库重构 |
| git fsck | 对象库完整性检查 |
| git fsck-objects* | 同义词，等同于 git fsck |
| git gc | 版本库存储优化 |
| git index-pack | 从打包文件创建对应的索引文件 |
| git lost-found* | 过时，请使用 git fsck –lost-found 命令 |
| git pack-objects | 从标准输入读入对象ID，打包到文件 |
| git pack-redundant | 查找多余的 pack 文件 |
| git pack-refs | 将引用打包到 .git/packed-refs 文件中 |
| git prune | 从对象库删除过期对象 |
| git prune-packed | 将已经打包的松散对象删除 |
| git relink | 为本地版本库中相同的对象建立硬连接 |
| git repack | 将版本库未打包的松散对象打包 |
| git show-index | 读取包的索引文件，显示打包文件中的内容 |
| git unpack-objects | 从打包文件释放文件 |
| git verify-pack | 校验对象库打包文件 |

> 5.数据传输相关命令
| 命令 | 简要说明 |
| -------- | -------- |
| git fetch-pack | 执行 git fetch 或 git pull 命令时在本地执行此命令，用于从其他版本库获取缺失的对象 |
| git receive-pack | 执行 git push 命令时在远程执行的命令，用于接受推送的数据 |
| git send-pack | 执行 git push 命令时在本地执行的命令，用于向其他版本库推送数据 |
| git upload-archive | 执行 git archive –remote 命令基于远程版本库创建归档时，远程版本库执行此命令传送归档 |
| git upload-pack | 执行 git fetch 或 git pull 命令时在远程执行此命令，将对象打包、上传 |

> 6.邮件相关命令
| 命令 | 简要说明 |
| -------- | -------- |
| git imap-send | 将补丁通过 IMAP 发送 |
| git mailinfo | 从邮件导出提交说明和补丁 |
| git mailsplit | 将 mbox 或 Maildir 格式邮箱中邮件逐一提取为文件 |
| git request-pull | 创建包含提交间差异和执行PULL操作地址的信息 |
| git send-email | 发送邮件 |

> 7.协议相关命令
| 命令 | 简要说明 |
| -------- | -------- |
| git daemon | 实现Git协议 |
| git http-backend | 实现HTTP协议的CGI程序，支持智能HTTP协议 |
| git instaweb | 即时启动浏览器通过 gitweb 浏览当前版本库 |
| git shell | 受限制的shell，提供仅执行Git命令的SSH访问 |
| git update-server-info | 更新哑协议需要的辅助文件 |
| git http-fetch | 通过HTTP协议获取版本库 |
| git http-push | 通过HTTP/DAV协议推送 |
| git remote-ext  | 由Git命令调用，通过外部命令提供扩展协议支持 |
| git remote-fd | 由Git命令调用，使用文件描述符作为协议接口 |
| git remote-ftp  | 由Git命令调用，提供对FTP协议的支持 |
| git remote-ftps | 由Git命令调用，提供对FTPS协议的支持 |
| git remote-http | 由Git命令调用，提供对HTTP协议的支持 |
| git remote-https |由Git命令调用，提供对HTTPS协议的支持 |
| git remote-testgit | 协议扩展示例脚本 |

> 8.版本库转换和交互相关命令
| 命令 | 简要说明 |
| -------- | -------- |
| git archimport | 导入Arch版本库到Git |
| git bundle | 提交打包和解包，以便在不同版本库间传递 |
| git cvsexportcommit | 将Git的一个提交作为一个CVS检出 |
| git cvsimport | 导入CVS版本库到Git。或者使用 cvs2git |
| git cvsserver | Git的CVS协议模拟器，可供CVS命令访问Git版本库 |
| git fast-export | 将提交导出为 git-fast-import 格式 |
| git fast-import | 其他版本库迁移至Git的通用工具 |
| git svn Git | 作为前端操作 Subversion |

