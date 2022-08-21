# Git 操作

1.在进行任何的git操作之前，都得先切换到 Git 的仓库目录。

进入目录后右键Git Bash here

<img src="C:\Users\DELL\AppData\Roaming\Typora\typora-user-images\image-20220820183249597.png" alt="image-20220820183249597" style="zoom: 50%;" />

![image-20220820211616915](C:\Users\DELL\AppData\Roaming\Typora\typora-user-images\image-20220820211616915.png)

git init初始化Git仓库   git add xxx添加缓存区以免报错（并没有添加Git仓库中）git status查询仓库状态（经常用便于了解）git commit 提交命令（根据需要查询）（提交可能需要认证--在git文件中找到config打开添加如下）

![image-20220821084206037](C:\Users\DELL\AppData\Roaming\Typora\typora-user-images\image-20220821084206037.png)

![image-20220821084922803](C:\Users\DELL\AppData\Roaming\Typora\typora-user-images\image-20220821084922803.png)

![image-20220821085119565](C:\Users\DELL\AppData\Roaming\Typora\typora-user-images\image-20220821085119565.png)

git branch查看仓库分支（*代表当前所在分支-主分支）git checkout a切换分支a，此时最右边分支改变。git checkout -b b创建分支b后直接切换

![image-20220821085612922](C:\Users\DELL\AppData\Roaming\Typora\typora-user-images\image-20220821085612922.png)

切换回master分支，git merge a将a合并到master分支。git branch -d a删除a分支（如果没合并到主分支git branch -D强制删除）git tag xxx添加标签git tag 查看标签git checkout xxx切换到标签

# 连接Github

生成ssh key输入ssh-keygen -t rsa。Git Gui中heip-show ssh key公匙添加到Github中

验证ssh -T git@github.com![image-20220821093013233](C:\Users\DELL\AppData\Roaming\Typora\typora-user-images\image-20220821093013233.png)

# 提交代码

本地上传（本地更新）

```
git push origin master
```

本地下载（远程代码有更新）

```text
git pull origin master
```

一般先pull后push以免冲突

**1.本地没有Git仓库**

将远程仓库clone本地，直接就是Git仓库，不用init初始化了，只需在这个仓库修改然后commit

![image-20220821100714335](C:\Users\DELL\AppData\Roaming\Typora\typora-user-images\image-20220821100714335.png)

![image-20220821100821319](C:\Users\DELL\AppData\Roaming\Typora\typora-user-images\image-20220821100821319.png)

先在仓库复制下ssh链接（https不支持没了解原因）新建一个文件夹右键进git bash

 git clone xxx（ssh链接）文件夹中有了Github上的仓库了。

上传文件先把文件移过去，这时仓库状态显示文件未被追踪（没commit）之前写了commit之前要add

git add src/（文件夹要/）然后git commit -m "commit src file"

提交完了该push了git push origin master(注意，现在Github默认分支main，master改main)

![image-20220821134430373](C:\Users\DELL\AppData\Roaming\Typora\typora-user-images\image-20220821134430373.png)

**2.本地有Git仓库，多次commit操作**

建立仓库，初始化，输入git remote add origin xxx（链接）关联远程仓库，git pull origin master同步到本地。

移文件，add，commit，push。又上去了。