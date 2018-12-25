it is a first git belong to huke
let is do it

					chapter one

one lesson
git init //初始化一个git仓库
git add [file] //添加文件
git commit -m"message" //上传文件输出原因

two lesson
git status //当前git工作区的状态
git diff //查看修改的git内容

three lesson
git log //查看更新版本信息头部有版本号,穿梭前使用
git reset --hard <版本号或者HEAD^> //HEAD指向的版本就是当前版本
git reflog //重返未来，查找历史命令

four lesson
git存在三个区：工作区，暂存区，master
撤销修改的几个场景：
1、只在工作区修改，未add到暂存区：git checkout -- <file>
2、在工作区修改，并add到暂存区，但是没有commit到master：
	git reset HEAD <file> //既可以回退版本，也可以把暂存区的修改回退到工作区
	git checkout -- <file> 
3、已经commit到master，但没有push：
	回退版本，参照three lesson

five lesson
git rm [file] //删除文件

                 chapter two
git远程仓库
git是一个分布式版本系统，在没有互联网的情况下也可以正常工作。
当有网络后，可以再把本地提交push完成同步。

在GitHub上免费获得远程仓库
one step：创建SSH Key //$ ssh-keygen -t rsa -C "youremail@example.com"
		  获得id_rsa(私钥)，id_rsa.pub(公钥)
two step:登录GitHub，打开Account setting -->add SSH Key 填写id_rsa.pub
本地仓库与gitHub仓库远程协作
先本地，后远程
one step：在GitHub上创建新项目
two step：$ git remote add origin git@github.com:michaelliao/learngit.git
		  $ git push -u origin master
先远程，后本地
one step:在GitHub上创建新项目
two step:$ git clone [项目名]

				 chapter three 分支
one lesson
创建分支：
git branch //查看分支
git branch <name> //创建分支
git checkout <name> //切换分支
git checkout -b <name> //创建+切换分支
git merge <name> //将分支合并到master
git branch -d <name> //删除分支

two lesson
当有冲突的时候，先解决冲突，再提交
git log -- graph //查看分支合并图

three lesson
fast forward模式下，删除分支，会丢掉分支信息
禁止ff模式，git会在merge时生成一个新的commit，这样就可以查看到分支信息了
git merge --no--ff -m "" <name>

four lesson
当不想合并代码时，又想去其他分支修改代码：
git stash //储存当前工作
git stash list//查看工作存取在哪里
git stash appy //恢复后stash不删除
git stash drop //删除存储的工作区
git stash pop //恢复同时删除stash内容

five lesson
git remote -v //查看远程库信息
本地新建的分支如果不推送到远程，对其他人就是不可见的；
从本地推送分支，使用git push origin branch-name，如果推送失败，先用git pull抓取远程的新提交；
在本地创建和远程分支对应的分支，使用git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致；
建立本地分支和远程分支的关联，使用git branch --set-upstream branch-name origin/branch-name；
从远程抓取分支，使用git pull，如果有冲突，要先处理冲突。

git push origin :<name> //删除orgigin里的分支

six lesson
git rebase <branch> //将历史整理成直线
rebase会把之前分支里的每个提交取消，并把他们临时保存为补丁（补丁保存在.git/rebase目录中）
然后把分支更新到最新的“origin”，然后再把补丁运用到分支中。
之前的提交被删除。
git rebase --continue //继续应用余下补丁
git rebase --abort //终止rebase，回到之前状态

				 chapter three

git tag <name> //打新标签，默认是打在最新提交的commit上



