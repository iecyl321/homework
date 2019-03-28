#echo "# homework" >> README.md
#git init
#git add README.md
#git commit -m "first commit"
#git remote add origin https://github.com/iecyl321/homework.git
#git push -u origin master


Git 常用命令使用

1）、本地库初始化 git init

2）、设置签名

作用：区分不同开发人员的身份。

说明：这里设置的签名和登录远程库（代码托管中心）的账户没有关系。

a)、项目级别签名:

git config user.name [AAA]

git config user.email [邮箱地址]

签名信息位置：cat .git/config

b)、系统级别签名:

git config --globaluser.name [AAA]

git config --global user.email [邮箱地址]

签名信息位置：cd ~ 、cat .gitconfig

3）、基本操作

a)、查看状态： git status(查看工作区、暂存区的状态)

b)、添加操作: git add 文件名(将工作区新建/修改的内容添加到暂存区)

c)、提交操作： git commit -m “commit message” 文件名(将暂存区的内容提交到本地库)

4）、查看历史记录

a)、git log

b)、git log --pretty=oneline

c)、git log --oneline

d)、git reflog (HEAD@{移动到当前版本需要多少步})

5）、前进和后退

a)、基于索引值的操作（推荐做法）

git reset --hard 哈希索引值

示例：找回删除状态已经提交本地库的文件操作。

b)、使用^符号 （只能后退，一个^表示后退一步）

git reset --hard HEAD^

c)、使用~符号 （只能后退，n表示后退n步）

git reset --hard HEAD~2

6）、比较文件差异

a)、git diff [文件名] (将工作区中的文件和暂存区的进行比较)

b）、git diff [本地库历史版本] [文件名] (将工作区中的文件和本地库历史记录比较，不带文件名的话，会比较多个文件)

7）、分支管理

在版本控制过程中，使用多条线同时推进多个任务。





分支的优势？

a)、同时并行推进多个功能开发，提高开发效率。

b)、各个分支在开发过程中，如果某个分支开发失败，不会对其他分支有影响，失败的分支可以删除，然后重新开始即可。

分支常用命令：

a)、git branch -v （查看本地库中的所有分支）

b)、git branch dev (创建一个新的分支)

c)、git checkout dev （切换分支）

d)、分支合并

i)、切换到接收修改的分支

git checkout master

ii)、执行merge命令

git merge dev

（注：切换分支后，在dev分支中做出的修改需要合并到被合并的分支master上)

8）、冲突解决

当一个分支的内容和另一个分支的内容不同时，此时任一分支合并另一分支过程中就会出现冲突。




冲突的解决办法：

a)、编辑文件，删除特殊符号。

b）、将文件修改完毕后，保存退出。

c)、git add [文件名]。

d)、git commit –m “日志信息”。

注意：此时commit时不能带文件名。