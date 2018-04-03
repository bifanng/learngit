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

---------------分割线-------------
删除文件
rm file 删除工作区文件  git status查看，提醒工作区文件被删除。
git rm file 删除版本库文件并且git commit提交
git checkout -- file恢复最新提交到版本库的版本。
工作区文件被误删，版本库还有，可将版本库版本替换工作区版本，“一键还原”
-----------------分割线----------------

------------远程数据库添加--------------
注册github网站：名称bifang 492859117@qq.com 密码：123072340qq

ssh-keygen -t rsa -C "email@example.com"填写自己在github上的邮箱，生成key。主目录下自动生成id_rsa和id_rsq.pub私钥和公钥key。将公钥添加到github上后可以往github上的免费仓库推送。
关联远程使用命令：git remote origin git@server-name:path/repo-name.git 其中的origin为远程库的名字，默认取为origin为u远程库，server-name为github.com   path为hgithub注册远程库的用户名  repo-name为本地版本库的名称。
git push -u origin master 第一次推送master分支的所有内容，-u推送本地内容到远程，并且关联本地和远程，以后推送拉取简化命令。
此后 提交使用git push origin master推送最新的修改。
----------------------------------------------

---------------------克隆版本库-------------
在github上新建版本库后 使用git clone git@server-name：username/repository-name.git克隆。
git支持多种协议 包括https 但通过ssh支持的原生态git协议速度更快

--------------创建与合并分支--------------
说明：如果代码较多，直接在版本库上书写，可能因为代码不完整影响工作，现在提出分支概。自己创建分支，版本库仍然使用当前版本库工作，自己分支代码书写完成，再合并就能使用最新版本库。。
版本库每次提交git将其串成一条线，叫主分支为master分支，master指向最新提交，HEAD指向master，每次提交master向前进一步。当创建新的分支dev时，指向master相同的最新提交，再把HEAD指向dev，表示当前在dev分支上。现在开始，对工作区的修改和提交针对dev分支，而master指针不表，dev向最新移动。dev工作完成后再合并到master上，讲master指向当前dev提交就完成合并。将dev分支删除后，就只剩下一条master分支。
创建分支并切换git checkout -b dev   -b表示创建并切换 相当于：git branch dev 和git checkout dev
git branch 查看当前使用的分支。
合并git merge dev 
删除分支 git branch -d dev

---------------冲突-------------
如果两个分支都对一个文件进行了修改提交合并。将会出现冲突，git讲无法进行快速合并。
思路：合并时出现问题，先人为的进行冲突解决，再提交，合并完成。
使用git log --pragh --pretty=oneline --abbrev-commit查看合并图
