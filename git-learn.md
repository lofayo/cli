> 对于计算机中涵盖知识的庞大，我们无从想象。有人说，对于很多东西你只要会用就行了，不用怎么理解，但对于我的感觉是没理解的知识用得总是不踏实，心中空落落的，况且理解了才能创造性的使用。虽然理解的路上会有点慢，但是它会变成你自己的东西。

###git命令
> 虽然`git`命令不是特别多，理解后用起来也不是特别难，但就是为什么它的英文与我们理解的汉语意思差距那么大？不信走着瞧

注：下面所有命令先都得切换到对应目录下

1. `git init`	初始化`git`仓库

2. `git add <file name>` 添加文件到缓存区。可以一个一个文件的添加，还可以所有文件一起添加 `git add .` 或者 `git add -A`

3. `git commit -m 'description message'` 一次性提交所有缓存区文件到仓库。这里的`-m`表示提交的备注内容，比如：添加了什么内容

4. `git status`	随时掌握工作区内容状态

5. `git diff`	如果`git status`显示内容被修改，可以用`git diff`查看内容间区别

6. `git log`	查看提交的内容版本

7. `git reset --hard commit_id `	回到某个历史版本

8. `git reflog`	查看命令历史

9. `cat readme.txt`	查看该文件的内容（这个地方很奇怪吧，查看文件内容竟然用 cat 命令，在我的英文世界里从来不知道 cat 还能有这层含义。就算是现在打开有道词典查，也依然找不到cat 可以表示查看的意思。表示查看有那么多单词可以选，像look,view,check...，怎么偏偏就选中‘猫了’，你是怎么想的）

10. `get checkout -- fileName` 抛弃工作区的修改（同理checkout也没有很清晰的表明这一层含义的）

11. `get reset head fileName`	想抛弃修改过的内容，但是已经提交到了缓存区，该命令用于由缓存区退回到工作区，再利用上一条命令抛弃修改的内容

12. `rm fileName`	删除工作区某个文件，这个时候工作区文件就和仓库里区的文件不相同了，这个时候就有两种可能：确定要删除（删掉仓库区里该文件），还会从仓库区里恢复该文件。



 
**确定删除：** `git rm fileName`----> `git commit -m 'description'`

**从仓库区恢复文件：** `git checkout -- fileName`
(其实，我就不太理解，恢复文件为什么要用`checkout`，这个单词有这层含义吗？)

### 远程仓库
将自己本地仓库文件和远程`github`仓库上的文件关联起来，实现实时更新，本地代码的修改提交，建立远程连接后，最后可以一次性`push`到远程仓库

首先，在`github`账号下，添加电脑的 SSH Key值，这个值是通过在`git bash`敲击命令生成的，如： `ssh-keygen -t rsa -C '870876711@qq.com'`。在`git bash`当前目录下找到`.ssh`文件，复制`id_rsa.pub`内容

其次，将该值添加到`github`账号下的`SSH Key`设置里。只有设置了key值关联，才有可能将本地仓库代码提交到`github`的远程仓库里
 
最后，在`github`下创建 `repository`，命令行工具下，实现本地仓库与远程仓库的连接`git remote add origin git@github.com:lofayo/cli.git` ----> `git push -u origin master`第一次推送，将master分支推送到远程master分支上，以后推送命令就简单些`git push origin master`

克隆，命令比较简单`clone git@github.com:lofayo/cli.git`

### 创建与合并分支
对分支的理解：就像我们高考做数学大题，先在草稿纸上写出计算过程看看对错，对了话再誊写到答题卡上。分支道理差不多，现在原文件下建立个分支，在那上面想怎么写就怎么写，最后项目写完了，也没有bug了在合并到主分区上

1. `git branch`	查看分支

2. `git branch name`	创建分支

3. `git checkout name`	切换分支

4. `git checkout -b name`	创建+切换分支

5. `git merge name`	合并分支到主分支上

6. `git branch -d name` 分支合并后，就可以删掉分支