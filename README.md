##Git Flow 学习

###1. Git 优点
> * 分布式，所有本地库包含了远程库的所有内容
> * 优秀的分支模型，切分支，合并分支，极其方便
> * 最大的优势，就是快速。相比于其他版本工具，在切分支和合并分支方面很快。

### 2.版本工具控制中需要面对的问题
1. 如何开始一个Feature的开发，而不影响别的Feature？
2. 由于很容易创建新分支，分支多了如何管理，时间久了，如何知道每个分支是干什么的？
3. 哪些分支已经合并回了主干？
4. 如何进行Realease的管理？开始一个Release的时候，如何冻结Feature，如何在Prepare Release的时候，开发人员可以继续开发新的功能？
5. 线上代码出Bug了，如何快速修复？而且修复的代码要包含到开发人员的分支以及下一个Release？

###3.咱们的优点和问题
####优点####


```
（1）项目不大
（2）开发人员不多
（3）生产发布简单直接
（4）分支一个master和一个develop（test）相对简单操作
（5）不涉及代码发版问题
```

####存在的问题####

```
（1）开发时，容易产生冲突
（2）发布到生产环境的代码不纯粹
（3）开发和测试环节没有分开
（4）develop分支含未开发完的Feature
（5）等等
```

###4.Git Flow###
我们知道，写代码是要遵循一定的代码规范的，而代码管理同样需要一个清晰的流程和规范。
我们总是很幸运，能够站在巨人的肩膀上，Vincent Driessen经过实践写了一篇文章[A Successful Git Branching Model](http://nvie.com/posts/a-successful-git-branching-model/)

下面是Git Flow的流程图:

![](gitflow.png)
    
####Git Flow常用分支####
1. Production 分支
```
也就是我们经常使用的Master分支，这个分支最近发布到生产环境的代码，
最近发布的Release， 这个分支只能从其他分支合并，不能在这个分支直接修改
```
2. Develop 分支
```
这个分支是我们是我们的主开发分支，包含所有要发布到下一个Release的代码，这个主要合并与其他分支，比如Feature分支
```

3. Feature 分支
```这个分支主要是用来开发一个新的功能，一旦开发完成，我们合并回Develop分支进入下一个Release
```
4. Release分支
```当你需要一个发布一个新Release的时候，我们基于Develop分支创建一个Release分支，完成Release后，我们合并到Master和Develop分支
```

5. Hotfix分支
```
当我们在Production发现新的Bug时候，我们需要创建一个Hotfix, 完成Hotfix后，我们合并回Master和Develop分支，所以Hotfix的改动会进入下一个Release```








