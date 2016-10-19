# git-command
record git command used in work

* 一、远程仓库相关命令


* 二、本地仓库相关命令


* 三、远程分支相关命令


* 四、本地分支相关命令



**1. 查看远程仓库：**

`
git remote -v
`

  比如在我们的项目中就能返回：
  
```
E:\projects\im-h5>git remote -v
origin  git@gitlab.it.ikang.com:fuchao.zheng/im-h5.git (fetch)
origin  git@gitlab.it.ikang.com:fuchao.zheng/im-h5.git (push)
sae     https://git.sinacloud.com/ikangtjb (fetch)
sae     https://git.sinacloud.com/ikangtjb (push)
```

**2. 在本地创建一个远程仓库中已有的分支，并且创建对这个分支的跟踪：**

比如，远程仓库中已有一个V1.2.0的分支，我想要在本地创建一个V1.2.0分支，并且创建对这个分支的跟踪，可以使用以下命令：

`
git checkout --track origin/V1.2.0
`

返回如下结果：

```
E:\projects\im-h5>git checkout --track origin/V1.2.0
Branch V1.2.0 set up to track remote branch V1.2.0 from origin.
Switched to a new branch 'V1.2.0'
```

使用这个命令应该也可以实现这个效果（没有试过）：

`
git checkout -b V1.2.0 origin/V1.2.0
`

**3. 本地仓库创建一个新分支，并立即切换到新分支：**

比如，在本地仓库新建一个“wxTest”的分支，并立即切换到该分支：

`
git checkout -b wxTest
`

**4. 在远程仓库中创建一个新分支**

比如，要在远程仓库中创建一个叫做“wxTest”的分支：

