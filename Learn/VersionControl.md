# 版本控制软件的基础功能

1. 保存和管理同一文件生成的不同版本的文件

2. 提供客户端工具进行访问

   访问软件再访问指定版本的文件（让人感觉只是一个文件）

3. 提供不同版本文件的对比功能

# 集中式版本控制

中央服务器（统一资源库）

多人协作开发，可以从中央服务器下载资源和上传资源

缺点：文件冲突，多用户文件同时下载，异时上传，中央宕机会拖慢其他开发

VSS软件：对文件修改加锁

CVS，SVN：文件行数修改约束，各用户可以修改自己约束的一行，可以比对合并

# 分布式版本控制

再集中式版本控制下需要在本地建立一个对应的本地的资源库

# Git介绍（分布式版本控制）

## 本地仓库

`.git`文件夹下的`objects`文件夹就是本地仓库

每次 `commit` 后会给每个文件生成 40个16进制组成的`版本号`（提交码）可以通过`版本号`从`objects`文件夹下找到对应的 `commit` 后的提交信息

多人协作下、多人不同时间点的过多的`commit`会产生大量的提交信息,导致拖慢文件比对和版本控制的速度,会产生较多的`commit`冲突

引用`branch`:每个大模块的改动在自己对应的`branch`下操作，大模块完全完成后再对不同的`branch`合并,来减少`main branch`的`commit`的提价信息和冲突

合并分支`Choose a branch to merge into main`

不同分支存在相同文件名的文件：人工解决冲突