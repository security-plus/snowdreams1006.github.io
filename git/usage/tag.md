# 里程碑式标签

软件或项目的生命周期必不可少的一环就是**发布新版本**,通常习惯性命名为`v0.0.1` `v1.0.0` 之类的,这种时刻的项目代表着软件已开发到一定阶段,相当于历史的里程碑!

里程碑式诞生是由相关领导建立的,一段时间后觉得产品比较成熟了,是时候快速推向市场,因此命名版本号,或者代号.由于里程碑概念天生自带辨识度,因此我们很容易将不同时期的里程碑区分出来,就像历史事件一样,重大事件很多,每一件重大历史事件都有自己的名称和时间,里程碑也有自己特有的代号.

在 `git` 进行**版本控制**的过程中,一直在产生版本号,不过那都是无意义的随机字符串,这些版本号作为核心基础必不可少,而版本号又带有节点关系,几乎总是有上级节点,从而形成提交历史树.

我们的里程碑概念也应该离不开内置的版本号,只要对某一个版本号做下相关标记,就能顺着该标记指向的版本号依次往前推,从而能够追溯到源头.

这种需求是不是和我们前面说的分支概念很相似,同样是特殊的版本号,从而收集到一系列的历史版本,最终形成独立的提交历史线,但分支并不适合里程碑概念,为什么?

分支的诞生适合多人协作开发时互不影响,需要时再主动合并的工作模式,实质上是临时的,并不打算一直保留该分支,分支的目的是为了开发独立功能,功能开发完毕后也就没有分支存在的必要了,正是这种特点决定了分支不适合做里程碑,因为里程碑代表着过去重要时刻,不能随意销毁或变更!

简单总结下里程碑的需求特点:

- 永远指向特定的历史版本,不应被随意移动或销毁.
- 自定义命名方式,能够被人轻易理解,杜绝无意义的命名.

显然,目前为止还没有接触到里程碑相命令(手动滑稽,不然我为啥要写这篇文章),言归正传,`git` 的里程碑是**标签**.

![git-tag-create.png](../images/git-tag-create.png)

由上述分析我们可知分支和标签的基本功能是相似的,相应的命令也是差不多的.

## 创建标签 `git tag <tag>`

```
git tag v0.0.1
```

![git-tag.gif](../images/git-tag.gif)

## 列出标签 `git tag`   

```
git tag 
```

## 显示标签 `git show <tag>`

```
git show v0.0.1
```

## 删除标签 `git tag -d <tag>`

```
git tag -d v0.0.1
```

## 推送标签 `git push origin <tag>`

```
git push origin v0.0.1
```

## 推送全部标签 `git push origin --tags`

```
git push origin --tags
```

## 删除远程标签 `git tag -d <tag>` `git push origin :refs/tags/<tag>`    

```
# 删除本地标签 
git tag -d v0.0.1

# 推送删除标签
git push origin :refs/tags/v0.0.1
```


