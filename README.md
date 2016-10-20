# git-command
record git command used in work

# 一、远程仓库相关命令

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


# 二、本地仓库相关命令



# 三、远程分支相关命令

**1. 查看远程分支**

`
git branch -r
`

在我的项目中输入以上命令，输出如下：

```
E:\projects\im-h5-wechat>git branch -r
  origin/HEAD -> origin/master
  origin/master
  origin/pre-prod
  origin/prod
  origin/root
  origin/test
  origin/uat
```

**2. 删除远程分支**

第一种方法：

`
git branch -r -d origin/branch-name
`

比如，我想删除远程仓库origin中的一个分支"wxTest"，用以下命令：

`
git branch -r -d origin/wxTest
`

在我的系统中输出如下：

```
E:\projects\im-h5-wechat>git branch -r -d origin/wxTest
Deleted remote-tracking branch origin/wxTest (was 11cc880).
```

看意思是：删除了对远程分支origin/wxTest的跟踪，我在网上查的也是说通过这种方式只是删除的本地对该远程分支的track。但是接下来我查看远程的分支，发现远程分支已经删除了。如下：

```
E:\projects\im-h5-wechat>git branch -r
  origin/HEAD -> origin/master
  origin/master
  origin/pre-prod
  origin/prod
  origin/root
  origin/test
  origin/uat
```

第二种方法：

`
git push origin :branch-name
`

冒号前面的空格不能少，原理是把一个空分支push到远端origin仓库下的branch-name分支，相当于删除了该分支。
在我的系统中的输出如下：

```
E:\projects\im-h5-wechat>git push origin :wxTest
To git@gitlab.it.ikang.com:fe/im-h5-wechat.git
 - [deleted]         wxTest
```

```
E:\projects\im-h5-wechat>git branch -r
  origin/HEAD -> origin/master
  origin/master
  origin/pre-prod
  origin/prod
  origin/root
  origin/test
  origin/uat
```

由上看出，确实可以删除远程的分支。

**3. 创建远程分支**

我想要在远程仓库origin中创建一个叫做"wxTest"的分支，步骤如下：

第一步，在本地仓库中创建一个叫做"wxTest"的分支。

`
git checkout -b branch-name
`

```
E:\projects\im-h5-wechat>git checkout -b wxTest
Switched to a new branch 'wxTest'

E:\projects\im-h5-wechat>git branch
  master
  prod
  root
  test
  uat
* wxTest
```

现在本地已经有了"wxTest"分支。

第二步，将本地"wxTest"分支push到远程仓库origin，这样就能在远程仓库中创建一个wxTest分支。

`
git push origin b1:b2
`

上面的命令表示将本地的b1分支push到远程仓库origin上的b2分支。如果origin中原本没有b2分支，就会新建一个叫做b2的分支。

```
E:\projects\im-h5-wechat>git push origin wxTest:wxTest
Total 0 (delta 0), reused 0 (delta 0)
To git@gitlab.it.ikang.com:fe/im-h5-wechat.git
 * [new branch]      wxTest -> wxTest

E:\projects\im-h5-wechat>git branch -r
  origin/HEAD -> origin/master
  origin/master
  origin/pre-prod
  origin/prod
  origin/root
  origin/test
  origin/uat
  origin/wxTest
```

通过上面的命令，可以看到，确实在origin上新建了一个wxTest分支。

# 四、本地分支相关命令

**1. 本地仓库创建一个新分支，并立即切换到新分支：**

比如，在本地仓库新建一个“wxTest”的分支，并立即切换到该分支：

`
git checkout -b wxTest
`

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

**3. 查看本地分支：**

`
git branch
`

在我的项目中执行这个命令，输出如下：

```
E:\projects\im-h5-wechat>git branch   
* master                              
  prod                                
  root                                
  test                                
  uat                                 
```

**4. 删除本地仓库的某一个分支wxTest**

`
git branch -d wxText
`


