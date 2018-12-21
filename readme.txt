it is a first git belong to huke
let is do it

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

