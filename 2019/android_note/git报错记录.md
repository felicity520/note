
报错一：
error: src refspec master does not match any
error: failed to push some refs to 'https://github.com/felicity520/Gitnote.git'

解决一：
git pull origin master
git push origin master

报错原因：
在哪里pull就在哪里push，push之前先git pull origin master，然后再git push origin master

报错二：
fatal: couldn't find remote ref master

报错原因：
致命：找不到远程引用主机
