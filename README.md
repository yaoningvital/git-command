# git-command
record git command used in work

**1. 查看远程仓库：**
`
    $ git remote -v
`
  比如在我们的项目中就能返回：
```
    E:\projects\im-h5>git remote -v
    origin  git@gitlab.it.ikang.com:fuchao.zheng/im-h5.git (fetch)
    origin  git@gitlab.it.ikang.com:fuchao.zheng/im-h5.git (push)
    sae     https://git.sinacloud.com/ikangtjb (fetch)
    sae     https://git.sinacloud.com/ikangtjb (push)
```

**2. 克隆某一个特定的远程分支：**
`
git clone -b <branch name> [remote repository address]
`
比如要克隆远程仓库中的V1.2.0分支到本地：
```
git clone -b V1.2.0 git@gitlab.it.ikang.com:fuchao.zheng/im-h5.git
```
