linux命令
cd filepath  进入目录文件
cd .. 退回上一级目录
cd ../.. 返回上两级目录
pwd 显示工作路径 
ls 查看目录中的文件
lstree 显示文件和目录由根目录开始的树形结构 
mkdir dir1 创建一个叫做 'dir1' 的目录' 
vi filename 创建并编辑文件
rm -f file1 删除一个叫做 'file1' 的文件' 
rmdir dir1 删除一个叫做 'dir1' 的目录' 
cp file1 file2 复制一个文件 
find / -name file1 从 '/' 开始进入根文件系统搜索文件和目录 、
bzip2 file1 压缩一个叫做 'file1' 的文件 
gunzip file1.gz 解压一个叫做 'file1.gz'的文件 
cat file1 从第一个字节开始正向查看文件的内容 
tac file1 从最后一行开始反向查看一个文件的内容 
head -2 file1 查看一个文件的前两行 
tail -2 file1 查看一个文件的最后两行

git命令
创建本地仓库：windows安装git Bash
cd filepath 想建立在哪的本地仓库地址
git init   初始化创建本地仓库
ls -ah查看被隐藏的目录
cd ~/.filename 进入filename

理解工作区、暂存区、本地仓库
工作区即操作区，暂存区是通过git add filename将文件添加至暂存区，本地仓库是通过git commit -m将文件添加至本地仓库
git status 查看工作区状态
git diff filename 查看文件修改内容
git log 查看提交日志，每次提交会生成一个版本有commit id
退回上一个版本: git reset --hard HEAD^ ， 多少个^,就退回前几个版本
git relog:记录每一次命令，查看commit id
git reset --hard commit id 指定回到commit id的版本
丢弃工作区修改：git checkout -- filename 
丢弃暂存区修改：git reset HEAD filename回到工作区，在丢弃工作区修改
在文件夹中删除了文件：rm filename,可通过git checkout -- filename恢复版本区里的，一键还原
但是git rm filename 删除版本区里的内容

运程仓库
1.cd ~/.ssh 进入ssh文件夹，ls: 查看是否有ssh key,文件夹里有id_rsa和id_rsa.pub秘钥; cat filename 查看秘钥
如果没有，创建ssh key：
ssh-keygen -t rsa -C"youremail@example.com"

2.登录Github, 打开登陆GitHub，打开“Account settings”，“SSH Keys”页面：
然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：
点“Add Key”，你就应该看到已经添加的Key：
当然，GitHub允许你添加多个Key。假定你有若干电脑，你一会儿在公司提交，一会儿在家里提交，
只要把每台电脑的Key都添加到GitHub，就可以在每台电脑上往GitHub推送了。

3. github上创建一个repository,仅填入repository名字为gitlearn，创建了gitlearn此仓库。
4.运行 git remote add origin git@github.com:vera66ll/gitlearn.git 把本地目录关联远程repository
git remote remove origin 取消本地目录关联的远程库
  此处远程库的名字是origin,是git的默认叫法。
5.把本地库所有内容推送到远程库：git push -u origin master
由于远程库是空的，因此第一次推送master分支时，加上了-u，既推送了本地master分支，还把本地master分支和远程分支关联起来。
从现在开始，只要本地做了提交，就可以通过命令git push origin master推送。

克隆仓库
要克隆一个仓库，首先必须知道仓库的地址，然后使用git clone @github.com:vera66ll/gitlearn.git命令克隆。（@github.com:vera66ll/gitlearn.git是仓库地址）

问题处理：
当出现
fatal: Unable to create 'E:/git_library/.git/index.lock': File exists.

Another git process seems to be running in this repository, e.g.
an editor opened by 'git commit'. Please make sure all processes
are terminated then try again. If it still fails, a git process
may have crashed in this repository earlier:
remove the file manually to continue.

输入：在.git同级目录，执行rm -f .git/index.lock 

create a new branch is quick