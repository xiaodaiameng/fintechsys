## 一、前端：

**Node.js**：是让 JavaScript 能在服务器上运行的基础环境。

**nvm**：Node.js 的版本管理工具，用于安装和切换多个 Node.js 版本。

**pnpm**：Node.js 的包管理工具，用于安装和管理Node.js项目的依赖。

**Astro**：是一个用 JavaScript/TypeScript 编写的、运行在 Node.js 环境之上的现代前端框架，用于高效地构建网站。

## 二、工作：

### （一）、**git**：

前言：

==Git的意义——版本控制==

==实现的手段——分支（即创造平行宇宙）==

#### 1、安装：

https://git-scm.com/install/

几乎都是next，一些可以看个人来改，比如下图。

![image-20251119210452021](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119210452021.png)

安装成功后可见：

![image-20251119211916581](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119211916581.png)

#### 2、配置

打开 git-bash.exe，

先**config**：配置一下自己的用户名、邮箱。

```
git config --global user.name "你的姓名"
git config --global user.email "你的邮箱@example.com"
```

查看所有配置的命令：git config --list

![image-20251119232019742](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119232019742.png)

#### 3、使用！！！

##### 1）在想要创建 Git 仓库的文件夹下进行**init **

在这个文件夹创建了一个空的 Git 仓库。就算这个文件夹里面本来就有文件，git也还不知道，只有add时才开始追踪。（提一嘴，现在只是在说本地仓库噢，远程仓库在后头哩。）

```
git init
```

![image-20251119232947801](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119232947801.png)

项目根目录下的  .git 隐藏文件夹 就是 Git 的“魔法后台”：它存储了将来这个文件夹下以后新建的文件夹的所有历史版本。

##### 2）添加要追踪的文件

```
git add 文件名
```

a. 比如添加一个md文件：

![image-20251119233009884](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119233009884.png)

就是把这个文件放到暂存区了！

（ 执行 add指定文件 时这个文件要在这个文件夹里 ）

b. 追踪此**文件夹**的所有动向（即添加此文件夹所有文件到暂存区的意思）就写：  

```
git add .
```

Git 的 `git add .` 只对**当时文件夹里已经存在**的文件有效。如果是在执行 `git add .` 之后才把文件拖进来的，那么需要重新执行一次。

![image-20251119233144423](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119233144423.png)

c. 交互式添加，git 会逐个显示每个变化块，问你是否要添加到暂存区。

```
git add -p
```

d. 如果发现待会不想提交的文件，可以从暂存区移除。

```
git restore --staged 不想提交的文件名
```

##### 3）**commit**：正式提交

正常提交示例：

```
git commit -m "暂存区里的东西现在提交上去，这是本次提交的描述信息。"
```

![image-20251119233422982](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119233422982.png)

==嘎嘣一下==，发现①代码缺了个点，或者②描述信息写错了，或者③漏提交文件，而且这个漏了的文件也是想要合并在这次提交里的，可以修改：

示例：比如一个 hello.py刚提交。然后出现上述问题。

①   git add hello.py

​       git commit --amend --no-edit

②   git commit --amend -m "新信息"

![image-20251119233603914](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119233603914.png)

③   git add 漏掉的文件 && git commit --amend --no-edit

简单记：`--amend` 的意思就是“修订一下我刚做的提交”。

##### 4）查看

a. 查看历史（git log只显示提交行为，不记录暂存区的内容）：

```
git log --oneline
```

![image-20251120000904964](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251120000904964.png)

b. 查看历史版本的文件

```
git show <提交哈希>:<文件名>
# 示例：
git show c744c63:fintechsys.md
```

==按q回家==，不然出不来了。

c. 还可以用对比模式看：

示例：对比 哈希号为c744c63的版本的 fintechsys.md与现在的 fintechsys.md，不管有没有在暂存区，直接被拿来对比了。

```
git diff c744c63 fintechsys.md
```

![image-20251120002018882](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251120002018882.png)

d. 查看文件状态

```
git status
```

e. 查看所有分支

```
git branch
带 * 号的就是你当前所在的分支。
```

##### 5）分支！！！

比如我的项目结构是：

fintechsys
│  draft.txt
│  fintechsys.md
│
└─littleTest
        helloGit.py

（tree解读：根文件夹叫做fintechsys，有两个散装文件和一个名为 littleTest的文件夹，文件夹里面有个文件。）

现在根目录 fintechsys就是默认的master分支

在 master 分支看原始文件：

```
git checkout master
```

如果想做个新分支，比如说想做一点有实验性的代码。（对我这个小白来说简直叫做闲来无事了属于是）

记得先提交当前的所有更改再创建新分支。

git add .
git commit -m "确保保存了文件夹的当前状态，接下来要创建新分支了。"

```
git checkout -b NAME

# 示例：创建并切换到名为 branch01的新分支
git checkout -b branch01
```

现在你就在一个新分支上了，任意修改和提交。

```
# 回到 master 分支：又能看到原始文件
git checkout master
```



#### 4、远程仓库

##### 1）自我介绍

![image-20251119233909696](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119233909696.png)

##### 2）关联远程仓库

先到自己账号new一个仓库再过来。

（ADD README 最好ON一下，让人更方便地认识这个仓库，刚刚忘记开了，现在又不知道怎么开。）

![image-20251120004401491](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251120004401491.png)

有了想要的远程仓库，可以开始关联了

```
git remote add origin 你的远程仓库的链接.git
# 示例
git remote add origin https://github.com/xiaodaiameng/fintechsys.git
```



学弟的友情提示：

![image-20251120010705826](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251120010705826.png)

















