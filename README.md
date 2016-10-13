# git-command
record git command used in work

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
