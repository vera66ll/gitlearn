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
