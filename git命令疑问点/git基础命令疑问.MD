# git基础命令疑问点

#### 1.git fetch和git pull的区别
> fetch命令是从远程获取最新代码到本地，不会自动merge，而pull命令会包含merge到本地。git fetch更安全些，因为在merge前，可以看下更新情况，然后再决定是否合并。