## Git​

### 一、git简介

Git是一个开源的**分布式版本控制系统**，可以有效、高速地处理从很小到非常大的项目版本管理。

#### 1.1 git结构

![git工作原理](img\git工作原理.png)

#### 1.2 常见单词
```java
// git结构
workspace：工作区
index / stage：暂存区
repository：本地仓库
remote：远程仓库

// 常用命令
add - 添加
commit - 提交
pull - 拉取
push - 推送
clone - 克隆
checkout - 检出
fetch - 抓取
```

### 二、git配置

#### 2.1 配置SSH

```Java
// 打开git bash，分别执行以下两句命令
git config --global user.name "pys"                // 用户名，任意
git config --global user.email "354510585@qq.com"  // github邮箱
```

以上命令执行结束后，可用 `git config --global --list` 命令查看配置是否OK 

```java
ssh-keygen -t rsa -C "354510585@qq.com"
```

生成`id_rsa`和`id_rsa.pub`两个文件，这两个就是SSH Key的秘钥对，`id_rsa`是私钥，不能泄露出去，`id_rsa.pub`是公钥，可以放心地告诉任何人。 

这两个文件的目录一般为 C:/Users/你的用户名/.ssh (mac: /Users/用户/.ssh）

#### 2.2 配置github

登陆GitHub，“Account settings”—“SSH Keys and GPG keys”—“New SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容即可。

```java
ssh -T git@github.com   // 测试是否配置好
```

### 三、git使用

#### 3.1 创建版本库

```
mkdir learngit
cd learngit
git init
git add readme.txt
git commit -m "wrote a readme file"
```

#### 3.2 远程仓库

方式一：添加远程库

```java
git remote add origin git@github.com:Y1SeN/Java.git
git pull origin master:master
git push -u origin master
```

由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令：`git push origin master`。

方式二：从远程库克隆

```java
git clone git@github.com:Y1SeN/Java.git
```

### 四、常用命令

![git常用命令速查表](img\git常用命令速查表.jpg)

### 五、参考链接

- 廖雪峰git教程： https://www.liaoxuefeng.com/wiki/896043488029600 
- git命令汇总： https://www.jianshu.com/p/46ffff059092 
- git原理及sourcetree使用：https://github.com/Mark24Code/15minGit/blob/master/15minGit2. 
- git以及github使用： https://www.jianshu.com/p/296d22275cdd 