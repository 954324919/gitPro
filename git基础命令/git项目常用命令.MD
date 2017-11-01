# git项目常用命令

#### 1.修改项目.gitignore,实现忽略特殊文件

> 有些时候,必须把某些文件放到git的工作目录中,但又不能提交它们,比如某些配置文件。在git工作区的根目录下创建一个特殊的.gitignore文件，然后把要忽略的文件名填进去,git会自动忽略这些文件。当然不需要重头开始写.gitignore文件，github已经准备了各种配置文件，只需要组合一下，所有配置文件可以直接在线浏览:https://github.com/github/gitignore

> 忽略规则：1.忽略操作系统自动生成的文件，比如缩略图等；2.忽略编译生成的中间文件、可执行文件，如果一个文件是通过另一个文件生成的，那自动生成的文件不会放进版本库，比如Java生成的.class文件；3.忽略自己带有敏感信息的配置文件。
> 在项目根目录下创建.gitignore文件,详细忽略实例查看该文件

#### 2.暂存区、工作区、本地仓库状态查看

> git status查看仓库的状态，在实际开发过程中在修改文件时会反复提交和修改，使用该命令可以清楚当前提交状态。

- Untracked files
  - 该提示是说你在本地添加了新文件，但是该文件git并不知道(该文件还没有add)
- Changes to be committed
  - 已经将文件add到暂存区，需要将文件提交到本地仓库(还没有commit)
- Changes not staged for commit
  - 该提示表示已经执行过add命令，添加到了暂存区，但是这些文件又修改了(没有执行commit)

> git暂存区理解及相关问题描述:http://selfcontroller.iteye.com/blog/1786644

#### 3.git rm使用

> 使用rm命令可以执行文件删除并从git仓库管理中移除(注意，最后使用git commit才真正提交到git仓库，git clean是将没有add的文件删除)。

- git rm <文件名>
  - 删除文件，并从仓库系统中移除。
- git rm -r <目录名>
  - 删除文件夹，并从仓库系统中移除。
- git rm --cached <文件名>
  - 如果文件已经通过add命令添加到了暂存区(还没有commit)，可以使用--cached命令把文件移除(类似clean命令)。
#### 注意：对于已经被git rm删除掉（还没被提交）的文件或目录，如果想取消其操作的话，可以首先通过git add -i的子命令revert从索引库中把它们剔除，然后用git checkout <文件>命令来达到取消的目录

#### 4.git stash使用

> 实际开发中如果当前工作区内容已被修改，但是还没有完成。需要切换分支去修改bug，但当前的内容还并不想提交，因为修改还没有完成。这时需要使用git stash(将修改的内容先add进暂存区)进行备份工作区。

- git stash list
  - 显示Git栈内的所有备份，可以利用这个列表来决定从那个地方恢复。例如使用'git stash apply stash@{1}'就可以将你指定版本号为stash@{1}的工作取出来
- git stash clear
  - 清空Git栈。此时使用gitg等图形化工具会发现，原来stash的哪些节点都消失了。


