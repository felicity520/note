添加文件
git add .

写入缓存
git commit -m 'first upload'

git remote rm origin

添加远程仓库
git remote add origin git@github.com:zhouxihi/ZXTabBarController.git

推送文件到远程仓库
git push -u origin master

将远程仓库里面的项目拉下来
git pull origin master 

帮助命令，后面加-h  或者是 git --help
比如：git rm -h

---------------------------------------------------------------------------------
在本地删除远程仓库：
参考博客：https://www.cnblogs.com/imyalost/p/9259149.html
1、拉取远程仓库的文件到本地：
git clone https://github.com/felicity520/note.git
PS：如希望将远程仓库的文件拉取到本地指定文件夹则需要先进入对应的文件夹目录下
cd D:/Software/
2、git rm -r file -r是递归删除
git status
3、提交修改后的文件到远程仓库
git commit -m ‘删除了file文件’
4、push到远程仓库
git pull origin master
git push origin master