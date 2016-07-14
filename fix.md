git使用常识

摘要

使用git要知道一些常识，或者说是技巧，包括怎么写commit -m信息

##一.<a name="commit"></a>只打包提交有关联的变更（COMMIT RELATED CHANGES）

commit应该是对相关变更的打包，比如修复两个不同的bug应该是两个独立的commit，这样更细致的commit能让其他开发者更容易理解变更并在出错的时候轻松回滚。Git中的暂存区和暂存能力其实只是某个文件的一部分，所以很容易就能创建粒度很细的commit。

##二.经常提交（COMMIT OFTEN）

经常提交能保证每个commit足够细致，而且有助于保证只打包提交有关联的变更。更重要的是，还允许你经常和别人共享代码。这样每个人都能更轻松地周期性地集成变更，避免merge冲突，相反地，如果只有几个重大commit还很少共享，就很难处理merge冲突。

##三.不要提交没干完的活儿（DON‘T COMMIT HALF-DONE WORK）

应该只commit成品代码，并不是要求commit前必须要做完整个大功能模块，恰恰相反，把整个功能模块的实现分割成逻辑块并记得经常尽早commit就好了，*切记不要*在每天下班前都习惯性的commit一下。如果想commit只是因为需要一个干净的工作区（为了检查某个分支，或者是想拉取变更等等），那可以考虑用Git的stash命令而不是commit。
You should only commit code when it‘s

##四.提交之前先测试（TEST CODE BEFORE YOU COMMIT）

不要自己觉得干完了就急着commit，应该彻底测试一遍确保真的干完了而且没有（你所知道的）副作用。把半成品commit到本地版本库里只会给自己带来麻烦，而要push或者共享代码给别人时，保证代码被测试过是非常重要的。

##五.认真填写提交信息（WRITE GOOD COMMIT MESSAGES）

commit信息应该以对所做变更的简短（建议不超过50个字符）总结开头，然后用空行把总结和下面的信息主体分开，信息主体应该详细解释以下问题：

1.  这次变更的原因是什么？

2.  和之前的实现有什么区别？

和git原生信息保持一致，例如git merge，应该用祈使句、一般现在时描述，不要用过去时态和单数第三人称形式。

##六.版本控制系统不是个备份系统（VERSION CONTROL IS NOT A BACKUP SYSTEM）

把文件备份在远程服务器上对版本控制系统来说是个极大的副作用，但不应该把VCS（版本控制系统）当备份系统来用，用CVS的时候，应该更多地注意commit的语义（详见[只打包提交有关联的变更](#commit)），不要只是单纯地塞满文件。

##七.多用分支（USE BRANCHES）

分支其实才是Git最强大的功能，这并非偶然：快捷的分支操作从一开始就是核心需求。分支是避免开发过程中各项工作相互混淆的完美工具，应该在开发工作流程中广泛使用分支：添新功能，改bug，试新想法……

##八.对工作流程达成一致（AGREE ON A WORKFLOW）

Git支持各种工作流程：long-running branches、Topic branches、merge或rebase、git流（git-flow）……到底选择哪一个取决于很多因素：具体项目、整体开发以及开发工作流程和（或许最重要的是）团队成员的偏好。无论选哪个，只要确保每个人都对工作流程达成一致就好。

##九.帮助文档（HELP & DOCUMENTATION）

可以方便地获取命令行帮助：git help <command>

##十.免费在线资源（FREE ONLINE RESOURCES）

-  Git Tower：<http://www.git-tower.com/learn>

-  Github简明指南：<http://rogerdudler.github.io/git-guide/>

-  Git官网：<http://www.git-scm.org/>

-  《Pro Git》：[百度网盘](http://pan.baidu.com/s/1eQs6C1c)，500+页的PDF，需要用高端功能的话可以翻书

###参考资料

-  [Git Tower：Version Control Best Practices](http://www.git-tower.com/blog/version-control-best-practices/)