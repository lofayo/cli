> 计算里很多东西都不是绝对的，而且有些东西你一认真就输了！

### git bash 窗口下的命令行cli(command line interface)：以下内容都是亲测可用
1. `cd : change directory`的简写，改变目录的意思，就是切换到哪个目录下， 如 `cd h:\xampp`  切换 `h` 盘下面的`xampp` 目录（只能是盘符下的一级目录），这样就不行 `cd h:\xampp\htdocs`

2. `cd ..` 回退到上一个目录， 注意，cd 和两个点点..之间有一个空格。

3. `pwd : print working directory`, 打印工作目录，它会显示我们当前所在的目录路径。

4. `ls: list` 都是列出当前目录中的所有文件。公司电脑`dir`列出目录，家里电脑就不行，估计有的电脑还是`ll`吧！（自己去试）

5.  touch : 新建一个文件 如 touch index.js 就会在当前目录下新建一个index.js文件。

6. `rm: remove`   删除一个文件, rm index.js 就会把index.js文件删除

7. `mkdir: make directory` 新建一个目录,就是新建一个文件夹. 如mkdir src 新建src 文件夹.

8. `rm -r` : 删除一个文件夹,  rm -r src 删除src目录， 好像不能用通配符。

9. `mv: mvoe` 移动文件, `mv index.html src`   index.html 是我们要移动的文件, src 是目标文件夹,当然, 这样写,必须保证文件和目标文件夹在同一目录下.  

*很多命令和`cmd`下差不多，但是也有区别，简单记录下，以示总结*
