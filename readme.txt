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


























