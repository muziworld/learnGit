# Git之创建本地仓库

## Step 1: 初始化

```bash
//新建一个文件夹
$ mkdir myLocalRepository
//初始化
$ git init	// 用 ls -ah 可以看到文件夹里多了一个.git文件
/* 版本控制系统只能跟踪文本文件的改动,比如 .txt, 网页，所有的程序代码等等，而word, 图片则不行 */
// 设置用户信息
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

##Step 2 ：建一个本地仓库

```bash
// 从工作区（work directory）提交到 暂存区（stage）
$ git add <file>	//比如： git add Git之创建本地仓库.md
// 从暂存区（stage）提交到 版本库（repository）
$ git commit -m "add Git之创建本地仓库.md"	//会将所有stage里面的文件提交到版本库（repository）
```

## Step 3 : 基本操作

```bash
//增
// 一般只需要新建文件，git add , git commit -m "message" 即可

//删
//删除工作区已经改乱的内容
$ git checkout -- <file>	//删除当前工作区的内容，并将对应的最新版本复制到工作区
$ git reset HEAD <file>	//把暂存区（stage）的修改撤销掉（unstage），重新放回工作区。
//删除文件
$ rm <file>	//在工作区删除文件
$ git rm <file> //在版本库中删除文件，
$ git commit -m "meesage"	//给出删除信息

//或者在工作区误删了
$ git checkout -- <file>	//从最新版本中恢复文件
//改
$ git reset --hard HEAD^ //退回上一个版本
$ git reset --hard <commit.id>	//退回指定版本，commit.id 可以通过 git log 查看或者通过 $ git reflog 查看历史的头（HEAD）指针

//查
$ git log 	//查看历史版本
$ git log --pretty=oneline	//简化显示
$ git reflog		//查看历史命令
$ git diff HEAD -- <file>	// 可以查看工作区（work directory与最新版本库的区别。
$ git status 	//查看工作状态
```