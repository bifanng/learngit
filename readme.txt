git is a version control system/
git is free software
git add readme.txt 是将文件添加到git库，必须要在库下的文件夹目录下创建文件
-m 后面输入得是本次提交s的m声明，可以输入任何内容
时光穿梭
version1
时光穿梭version2
时光穿梭version3 
HEAD指向版本为当前版本 git reset --hard commit_id
穿梭前使用git log查看提交历史
重返未来使用git reflog查看命令历史 确保版本
----------------------分割线----------------

git工作区与暂存区
git id a distributed version control system
git id free software distributed under the gpl
git has a mutable index called stage
---------------
git管理的是修改 而非是文件内容
比如c修改1，提交：add
再修改2，执行commit 状态为第二修改未提提交。工作区的第二次修改并未提交add
change1....
--------------
change2...
git 管理修改：文件在工作区修改，add提交后放入暂存区，commit提交到版本库。

--------------分割线----------
撤销修改
更改了工作区的文件内容时，想直接丢掉工作区的修改，使用git checkout -- file
更改了已add提交暂存区的文件内容时，想放弃修改，使用git reset HEAD file 回到第一步，状态为：修改了工作区内容，但未提交。重复第一步git checkout -- file 步骤即可
已经提交的commite版本库时，可根据版本id时光穿梭。
