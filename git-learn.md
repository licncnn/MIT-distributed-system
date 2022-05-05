<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220505082452981.png" alt="image-20220505082452981" style="zoom:53%;" />


xxx


Git 配置

```
git config -l 
系统配置
git config --sytstem --list 
用户global 配置
git config --global --list

```

```
$ git config --global --list
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
user.name=licncnn
user.email=57867286+licncnn@users.noreply.github.com
```

配置用户

```
git config  --global user.name "liyufeng"             // 在user目录下.gitconfig中
git config --global user.email fengncu@qq.com
```





Git 工作原理

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220505084645558.png" alt="image-20220505084645558" style="zoom:50%;" />

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220505084922608.png" alt="image-20220505084922608" style="zoom:50%;" />



<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220505085015072.png" alt="image-20220505085015072" style="zoom:50%;" />







Git项目创建

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220505085149909.png" alt="image-20220505085149909" style="zoom:50%;" />

一种方法是git clone 

```c
git init   
```



Git 文件状态

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220505085830921.png" alt="image-20220505085830921" style="zoom:50%;" />

实操 

````python
git status 
$ echo "hello world " > hello.txt

Administrator@DESKTOP-1NA6FF3 MINGW64 ~/Desktop/MIT-distributed-system (master)
$ git status
On branch master
No commits yet
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        hello.txt

//提交暂存区
git add .
// 提交到本次仓库
git commit -m "this is a message add a new file "

````



<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220505090544833.png" alt="image-20220505090544833" style="zoom:50%;" />



配置免密码登入

```
ssh-keygen

git clone ...
echo "readme" > README.md
git status 
git add .
git status 
git commit -m " add a  file"
git push / git push origin

```





Git多人开发

多分支、

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220505095004742.png" alt="image-20220505095004742" style="zoom:70%;" />

常用分支命令

```c#
git branch  //本地分支
git branch -r //远程分支
git branch dev //创建dev 开发分支
git checkout <branch>  切换到分支

// 合并分支
git merge [branch]

git branch -d [branch-name]    //删除分支 

//删除远程分支
git push origin --delete [branch-name]
git branch -dr [remote/branch]
```

如果一个人folk 提交了一个pull request . 诺他修改的那个 版本和现在的版本不一样 就会有冲突  

需要人来手动解决。解决冲突了再合并。

现实中 ， 我们可以对开发版本进行fork 进行push ，

由管理员 merge到主分支。

每个人也可以有自己的分支  ， 每次写代码前先从主分支pull代码，然后提交到自己的分支，由管理员merge到主分支然后发布。

主分支一般是发布版本。





```
git branch -M main 
git remote add origin https://github.com/licncnn/MIT-分布式系统.git
git push -u origin main
```



```
…或从命令行推送现有存储库
git remote add origin https://github.com/licncnn/MIT-distributed-system.git
 git branch -M main 
git push -u origin main
```



修改分支名字后

```
git branch -m main <BRANCH>
git fetch origin
git branch -u origin/<BRANCH> <BRANCH>
git remote set-head origin -a
```



进阶操作

```php
Administrator@DESKTOP-1NA6FF3 MINGW64 ~/Desktop/MIT-distributed-system/MIT-distributed-system (main)
$ git branch  test

Administrator@DESKTOP-1NA6FF3 MINGW64 ~/Desktop/MIT-distributed-system/MIT-distributed-system (main)
$ git branch dev

Administrator@DESKTOP-1NA6FF3 MINGW64 ~/Desktop/MIT-distributed-system/MIT-distributed-system (main)
$ git branch hotfix-406

Administrator@DESKTOP-1NA6FF3 MINGW64 ~/Desktop/MIT-distributed-system/MIT-distributed-system (main)
$ git checkout hotfix-406
Switched to branch 'hotfix-406'

Administrator@DESKTOP-1NA6FF3 MINGW64 ~/Desktop/MIT-distributed-system/MIT-distributed-system (hotfix-406)
$

```





