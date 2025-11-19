### 一、前端：

**Node.js**：是让 JavaScript 能在服务器上运行的基础环境。

**nvm**：Node.js 的版本管理工具，用于安装和切换多个 Node.js 版本。

**pnpm**：Node.js 的包管理工具，用于安装和管理项目依赖。

**Astro**：是一个用 JavaScript/TypeScript 编写的、运行在 Node.js 环境之上的现代前端框架，用于高效地构建网站。

### 二、工作：

**git**：

![image-20251119210452021](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119210452021.png)

![image-20251119210128050](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119210128050.png)

安装成功后可见：

![image-20251119211916581](C:\Users\ass\AppData\Roaming\Typora\typora-user-images\image-20251119211916581.png)

打开 git-bash.exe，

先**config**：配置一下自己的用户名、邮箱。

再在想要创建 Git 仓库的文件夹下进行**init **：在这个文件夹创建了一个空的 Git 仓库。现在只是个本地仓库噢，远程仓库在后头哩。

**add**：添加要追踪的文件，就是把这个文件放到暂存区了！（ 执行 add指定文件 时这个文件要在这个文件夹里）（ 追踪此文件夹的所有动向就git add .）

**commit**：正式提交

正常提交示例：

git commit -m "暂存区里的东西，现在提交上去，这是本次提交的描述信息。"

==嘎嘣一下==，发现代码缺了个点，或者描述信息写错了，或者漏提交文件，而且这个漏了的文件也是想要合并在这次提交里的，马上修改：

常用组合：

| 命令                                                 | 作用                                       |
| :--------------------------------------------------- | :----------------------------------------- |
| `git commit --amend -m "新信息"`                     | 修改上一次提交的信息                       |
| `git commit --amend --no-edit`                       | 将暂存区的更改加入上一次提交，且不修改信息 |
| `git add 漏掉的文件 && git commit --amend --no-edit` | 添加漏文件并合并到上一次提交               |

简单记：`--amend` 的意思就是“修订一下我刚做的提交”。















