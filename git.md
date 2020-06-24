# GIT

## git仓库

- 初始化版本库 


```git
git init
```

- 添加文件到版本库


```
git add

git commit
```

- 查看仓库状态


```
git status
```

## 远程仓库

### 创建ssh

- 创建ssh

```
ssh-keygen -t rsa –C “youremail@example.com”
```

- 拷贝id_rsa.pub

```
$ clip < ~/.ssh/id_rsa.pub
```

- 登录你的github账号，从又上角的设置（ [Account Settings](https://github.com/settings) ）进入，然后点击菜单栏的 SSH key 进入页面添加 SSH key。

- 点击 Add SSH key 按钮添加一个 SSH key 。把你复制的 SSH key 代码粘贴到 key 所对应的输入框中，记得 SSH key 代码的前后不要留有空格或者回车。当然，上面的 Title 所对应的输入框你也可以输入一个该 SSH key 显示在 github 上的一个别名。默认的会使用你的邮件名称。

- 测试ssh key

```
$ ssh -T git@github.com
```

### 添加远程库

- 登录github上，然后在右上角找到“create a new repo”创建一个新的仓库。

```
git remote add origin https://github.com/zhu-yl/testgit.git
git push -u origin master

```

- 把本地库的内容推送到远程，使用 git push命令，实际上是把当前分支master推送到远程。
- 由于远程库是空的，我们第一次推送master分支时，加上了 –u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。推送成功后，可以立刻在github页面中看到远程库的内容已经和本地一模一样了，上面的要输入github的用户名和密码

- 从现在起，只要本地作了提交，就可以通过如下命令：

```
git push origin master
```

### 从远程库克隆

- 克隆的库要公开
- 现在，远程库已经准备好了，下一步是使用命令git clone克隆一个本地库了。

```
git clone https://github.com/zhu-yl/testgit2
```

- 接着在本地目录下 生成testgit2目录了，克隆成功

### 从远程库更新

- 查看远程分支

使用如下命令可以查看远程仓库（我这里有一个origin仓库）

```
git remote -v
```

- 从远程获取最新版本到本地

使用如下命令可以在本地新建一个temp分支，并将远程origin仓库的master分支代码下载到本地temp分支

```
git fetch origin 
```

- 比较本地仓库与下载的temp分支

使用如下命令来比较本地代码与刚刚从远程下载下来的代码的区别：

```
git diff temp
```

对比区别之后，如果觉得没有问题，可以使用如下命令进行代码合并：

```
git merge temp
```

- 删除temp分支

如果temp分支不想要保留，可以使用如下命令删除该分支：

```
git branch -d temp
```

分支的代码之前没有merge到本地，那么删除该分支会报错，可以使用git branch -D temp强制删除该分支。

### 删除本地远程库重新获取

删除本地文件后，想从远程仓库中从新Pull最新版文件。
Git提示：up-to-date，但未得到删除的文件

原因：当前本地库处于另一个分支中，需将本分支发Head重置至master.

```
git checkout master 
git reset --hard
//git 强行pull并覆盖本地文件
git fetch --all  
git reset --hard origin/master 
git pull
```

## 创建与合并分支

查看分支：git branch

创建分支：git branch name

切换分支：git checkout name

创建+切换分支：git checkout –b name

合并某分支到当前分支：git merge name

删除分支：git branch –d name

### 分支冲突

合并分支出现冲突：git merge fenzhi1

查看状态：git status

查看冲突：cat readme.txt

修改冲突修改成一样，查看：cat readme.txt

查看分支合并的情况： git log

合并dev分支，使用命令：git merge –no-ff -m “注释” dev

通常合并分支时，git一般使用”Fast forward”模式，在这种模式下，删除分支后，会丢掉分支信息，现在我们来使用带参数 –no-ff来禁用”Fast forward”模式。

### bug分支

隐藏dev现场：git stash

主支上创建issue-404分支来修复bug。

```
git checkout -b issue-404
```

修复完切换到master分支 ,合并分支，删除分支

```
git checout master
git merge --no-ff -m "注释" issue-404
git branch -d issue-404
```

工作区是干净的，那么我们工作现场去哪里呢？我们可以使用命令 git stash list来查看下。

工作现场还在，Git把stash内容存在某个地方了，但是需要恢复一下，可以使用如下2个方法：

1.git stash apply恢复，恢复后，stash内容并不删除，你需要使用命令git stash drop来删除。
2.另一种方式是使用git stash pop,恢复的同时把stash内容也删除了。

## 多人协作

要查看远程库的信息 使用 git remote
要查看远程库的详细信息 使用 git remote –v

首先，可以试图用git push origin branch-name推送自己的修改.
如果推送失败，则因为远程分支比你的本地更新早，需要先用git pull试图合并。
如果合并有冲突，则需要解决冲突，并在本地提交。再用git push origin branch-name推送。

## git本地常见操作指令

### 创建git库

　　git init #在当前目录中生成一个.git 目录（含有.git目录的目录即是git仓库）

### 注册git用户

--->用于在团队合作开发中，表明代码作者。

　　git config --global user.name XXX #用户名

　　git config --global user.email XXX  #用户邮箱

　　git config --list #查看用户信息

注：加--global，全局设置。

### 向git库添加修改

　　git add [path］ #会把对应目录或文件，添加到stage状态
　　git add . #会把当前所有的untrack files和changed but not updated添加到stage状态

实际上是为修改内容添加index索引。

### 向版本库提交修改

　　git commit –m “XXXX”   #提交修改,添加注释

注：git 提示： 未有add红色字体，未有commit绿色字体，已提交则worktree是干净的

### 查看当前代码库的状态

　　git status

### 查看版本信息

　　--->实际是查看修改提交信息

　　git log

　　git log --graph #以图形化（节点）展示当前git库的提交信息。

### 查看指定版本信息

　　git show sdjf974654dd…. #(show后面为每次提交系统自动生成的一串哈希值)

　　git show sdji97 #一般只使用版本号的前几个字符即可

### 撤销修改

　　git reset
（1）撤销整体修改
git reset --hard #回到原来编辑的地方,改动会丢失。（同样适用于团队对于其他人
的修改恢复）

git reset --hard sdv143kvf…... #可回到指定的版本#(hard后面为每次提交系统自
动生成的一串哈希值)
   git reset [path] 会改变path指定的文件或目录的stage状态，到非stage状态。
   git reset 会将所有stage的文件状态，都改变成非stage状态。

（2）撤销某次修改
  回退1个change的写法就是git reset HEAD^，
  2个为HEAD^^，
  3个为HEAD~3，以此类推。

### 向远端库推送修改（提交修改）

　　git push origin 分支名

### 暂存修改

　　git stash可以把当前的改动（stage和unstage，但不包括untrack的文件）暂存。

　　然后通过git stash list查看。

　　并通过git stash apply重新取出来。但apply之前要保证worktree是干净的。

 

## Git团队开发常用操作指令

### 获取远端库项目

　　git clone/pull

### 团队开发的基本流程（多分支合并一个分支）

　　git add .  #添加改动的文件
　　git commit #（提交至本地）
　　git pull --rebase #（将服务器项目与本地项目合并）
　　git push  #（将本地项目上传至远端库）
　　（在提交前要git pull --rebase 一下，确保当前的本地的代码为最新。）

 

## Git 分支管理

### 建立分支

　　git branch AAA  #建立分支AAA

### 分支切换

　　git checkout AAA  #从当前分支切换到AAA分支 (若AAA分支不存在，则自动新建)

### 将分支与主枝master合并

　　git checkout master  #（首先切换回主枝）
　　git merge AAA  #（将分支AAA与主枝合并）

注：git merge：默认情况下，Git执行"快进式合并"（fast-farward merge），会直接将Master分支指向Develop分支。
　　使用--no-ff参数后，会执行正常合并，在Master分支上生成一个新节点。为了保证版本演进的清晰（保持提交曲线为直线），建议采用这种方法。

### 当前分支查看

　　git branch  #默认有master（也称为主枝）
　　git branch -r #查看远端库分支
　　git branch –a #查看当前所有分支（包括本地分支和远端库分支）

### 删除分支

　　git branch –d AAA  #删除分支AAA

### 切下远端库A分支到本地库A分支

　　git checkout -b A origin/A （若本地A分支不存在，则自动新建）

注：上面只是一些基本的操作命令，更多的命令可通过帮助文档查询。
     帮助文档的使用：
man git-<需查询的指令>   #（git后面有“-”）
   如commit的查询为 man git-commit



## 本地代码上传Github

1、Gtthub上建立远端仓库，复制下载链接。

2、本地指定目录下，Gitbash粘贴远端仓库下载链接拉取远端仓库代码。

3、复制本地需要提交的代码到远端仓库目录。

3、Git add、commit、push 提交本地代码至Github远端仓库。

 

## 在 github 上添加 SSH key 的步骤：

#### 1、首先需要检查你电脑是否已经有 SSH key 

运行 git Bash 客户端，输入如下代码：

```
$ cd ~/.ssh
$ ls
```

这两个命令就是检查是否已经存在 id_rsa.pub 或 id_dsa.pub 文件，如果文件已经存在，那么你可以跳过步骤2，直接进入步骤3。

 

#### 2、创建一个 SSH key 

```
$ ssh-keygen -t rsa -C "your_email@example.com"
```

代码参数含义：

-t 指定密钥类型，默认是 rsa ，可以省略。
-C 设置注释文字，比如邮箱。
-f 指定密钥文件存储文件名。

以上代码省略了 -f 参数，因此，运行上面那条命令后会让你输入一个文件名，用于保存刚才生成的 SSH key 代码，如：

```
Generating public/private rsa key pair.
# Enter file in which to save the key (/c/Users/you/.ssh/id_rsa): [Press enter]
```

当然，你也可以不输入文件名，使用默认文件名（**推荐**），那么就会生成 id_rsa 和 id_rsa.pub 两个秘钥文件。

 

接着又会提示你输入两次密码（该密码是你push文件的时候要输入的密码，而不是github管理者的密码），

当然，你也可以不输入密码，直接按回车。那么push的时候就不需要输入密码，直接提交到github上了，如：

```
Enter passphrase (empty for no passphrase): 
# Enter same passphrase again:
```

接下来，就会显示如下代码提示，如：

```
Your identification has been saved in /c/Users/you/.ssh/id_rsa.
# Your public key has been saved in /c/Users/you/.ssh/id_rsa.pub.
# The key fingerprint is:
# 01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db your_email@example.com
```

当你看到上面这段代码的收，那就说明，你的 SSH key 已经创建成功，你只需要添加到github的SSH key上就可以了。

 

#### 3、添加你的 SSH key 到 github上面去

**a、**首先你需要拷贝 id_rsa.pub 文件的内容，你可以用编辑器打开文件复制，也可以用git命令复制该文件的内容，如：

```
$ clip < ~/.ssh/id_rsa.pub
```

**b、**登录你的github账号，从又上角的设置（ [Account Settings](https://github.com/settings) ）进入，然后点击菜单栏的 SSH key 进入页面添加 SSH key。

**c、**点击 Add SSH key 按钮添加一个 SSH key 。把你复制的 SSH key 代码粘贴到 key 所对应的输入框中，记得 SSH key 代码的前后不要留有空格或者回车。当然，上面的 Title 所对应的输入框你也可以输入一个该 SSH key 显示在 github 上的一个别名。默认的会使用你的邮件名称。

 

### 4、测试一下该SSH key

在git Bash 中输入以下代码

```
$ ssh -T git@github.com
```

当你输入以上代码时，会有一段警告代码，如：

```
The authenticity of host 'github.com (207.97.227.239)' can't be established.
# RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
# Are you sure you want to continue connecting (yes/no)?
```

这是正常的，你输入 yes 回车既可。如果你创建 SSH key 的时候设置了密码，接下来就会提示你输入密码，如：

```
Enter passphrase for key '/c/Users/Administrator/.ssh/id_rsa':
```

当然如果你密码输错了，会再要求你输入，知道对了为止。

注意：输入密码时如果输错一个字就会不正确，使用删除键是无法更正的。

密码正确后你会看到下面这段话，如：

```
Hi username! You've successfully authenticated, but GitHub does not
# provide shell access.
```

如果用户名是正确的,你已经成功设置SSH密钥。如果你看到 “access denied” ，者表示拒绝访问，那么你就需要使用 https 去访问，而不是 SSH 。