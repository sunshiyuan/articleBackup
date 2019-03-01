---
title: git使用
date: 2019-03-01 07:13:34
tags:
---
![](2019-03-01-08-59-45.png)
You can do that like this:
nore只能忽略那些原来没有被track的文件，如果某些文件已经被纳入了版本管理中，则修改.gitignore是无效的。那么解决方法就是先把本地缓存删除（改变成未track状态），然后再提交：
git rm -r --cached .
git add .
git commit -m 'update .gitignore'
```
ls -a 显示所有文件夹  包括隐藏文件


git status  查看被修改的文件
 显示commit历史，以及每次commit发生变更的文件
git log --stat
查看文件修改的具体内容
git log -p 文件路径

<!-- more -->

### 撤销上次提交 
git log 找到想要撤销的操作之前的一次提交的commitid
 git reset --hard  commitid
如果提交到远程，需要将远程的分支代码也撤销
执行 git  push origin 分支名字 --force
// HEAD  指向master
// 为了覆盖掉远端的版本信息，使远端的仓库也回退到相应的版本，需要加上参数--force
git  push origin 分支名字 --force
git push origin HEAD --force

//新建远程分支
git checout -b develop
// 推到远程
git push origin develop

###配置忽略文件
1、在终端上进入项目，与.git文件并列的地方，执行vim .gitignore 操作（创建一个忽略文件）
vim .gitignore
2、https://github.com/github/gitignore/blob/master/Objective-C.gitignore
复制忽略文件
3、ESC退出  保存 wq
4：这个时候你发现，git status时你忽略的文件已经没有存在了。
如果按照上述方法定义后发现并未生效，原因是.gitignore只能忽略那些原来没有被track的文件，如果某些文件已经被纳入了版本管理中，则修改.gitignore是无效的。那么解决方法就是先把本地缓存删除（改变成未track状态），我一般都是删除所有缓存，不用单个删除，然后再提交：
git rm -r --cached .
git add .
git commit -m 'update .gitignore'

单个文件缓存删除：git rm -r --cached 文件地址

###单个 文件被修改了，但未执行 git add 
git checkout filename
git checkout .

###强制推送
git push -f origin master

### 关联远程仓库
git remote add origin  git地址

### 删除
git remote rm origin


### git项目配置
进入终端输入以下命令
1. 生成rsa秘钥对
2. ssh-keygen -t rsa -C '邮箱名字'
3. 提示生成
![](2019-03-01-09-01-34.png)
直接回车
4. 要求输入密码
![](2019-03-01-09-01-48.png)
可以不用输入
以上操作完成 生成公钥私钥对
![](2019-03-01-09-02-04.png)

5. 查看公钥内容   把公钥传到服务器
cat ~/.ssh/id_rsa.pub
6. 复制公钥      
pbcopy <  ~/.ssh/id_rsa.pub
将公钥复制到github上 SSH上进行配置
7. 测试ssh连接
ssh -T git@github.com
出现这个 添加成功
