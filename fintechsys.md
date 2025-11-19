## 一、前端：

**Node.js**：是让 JavaScript 能在服务器上运行的基础环境。

**nvm**：Node.js 的版本管理工具，用于安装和切换多个 Node.js 版本。

**pnpm**：Node.js 的包管理工具，用于安装和管理项目依赖。

**Astro**：是一个用 JavaScript/TypeScript 编写的、运行在 Node.js 环境之上的现代前端框架，用于高效地构建网站。

## 二、工作：

### （一）、**git**：

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

#### 3、使用

##### 1）在想要创建 Git 仓库的文件夹下进行**init **

在这个文件夹创建了一个空的 Git 仓库。就算这个文件夹里面本来就有文件，git也还不知道，只有add时才开始追踪。（提一嘴，现在只是在说本地仓库噢，远程仓库在后头哩。）

```
git init
```

![image-20251119232947801](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119232947801.png)

##### 2）添加要追踪的文件

```
git add 文件名
```

比如添加一个md文件：

![image-20251119233009884](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119233009884.png)

就是把这个文件放到暂存区了！

（ 执行 add指定文件 时这个文件要在这个文件夹里 ）

（ 追踪此**文件夹**的所有动向就写：   `git add . ` ）

![image-20251119233144423](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119233144423.png)

##### 3）**commit**：正式提交

正常提交示例：

```
git commit -m "暂存区里的东西现在提交上去，这是本次提交的描述信息。"
```

![image-20251119233422982](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119233422982.png)

==嘎嘣一下==，发现①代码缺了个点，或者②描述信息写错了，或者③漏提交文件，而且这个漏了的文件也是想要合并在这次提交里的，马上修改：

示例：比如一个 hello.py刚提交。然后出现上述问题。

①   git add hello.py

​       git commit --amend --no-edit

②   git commit --amend -m "新信息"

![image-20251119233603914](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119233603914.png)

③   git add 漏掉的文件 && git commit --amend --no-edit

简单记：`--amend` 的意思就是“修订一下我刚做的提交”。

##### 4）查看历史

最常用：简洁版历史：

```
git log --oneline
```



#### 4、远程仓库

1）前言：

![image-20251119233909696](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119233909696.png)

2）开始关联

















