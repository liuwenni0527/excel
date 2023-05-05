## 在项目中加入git控制

---



#### 介绍

每次要获取最新的代码，就直接从仓库上面pull下来

**我们仓库的地址是**：https://gitee.com/xie-anqi/bigtask.git

复制下来，在黑色窗口里面右键打开窗口点击`paste`就可以粘贴上去




#### 安装教程

1. 按这个教程安装好git：[(20条消息) Git的安装教程_头秃怎么办的博客-CSDN博客_git安装](https://blog.csdn.net/weixin_44486583/article/details/122704375)

2. 按这个教程连接远程仓库，并且克隆项目：[gitee码云完整使用教程（部署与克隆） - Web1024 - 博客园 (cnblogs.com)](https://www.cnblogs.com/jpwz/p/12449391.html)

   - 提前注册码云

   - 从第2点：使用`git`在本地开始初始化开始，一直到`git push origin master`

   - `clone`的时候可能会弹出窗口让你输入用户名和密码，这里是填码云的用户名和密码（用户名可在个人主页查看，是 @ 后面的那一串

3. 平时提交代码的方法：

   ```
   git config --global user.name "用户名"
   git config --global user.email "邮箱账户名"
   // 先进行身份确认，这里的用户名和密码是第一步git的
   git stash
   // 因为是多人合作，为了避免提交时仓库里的内容已经被修改，所以先把代码放到暂存区
   git pull origin master
   // 获取仓库最新版本
   git stash pop
   // 将暂存区的代码放回本地
   git add .
   // 把内容添加到缓冲区
   git commit -m "备注，写清楚本次提交主要是干了些啥"
   git push origin master
   // 把缓冲区内容推送到仓库
   ```
   

为了避免`merge`的时候出现冲突，最好不要改其他人文件的代码（改了也有解决办法，就是去到出问题的文件里面，会看到有奇怪的几行代码，其中Updated upstream 和=====之间的内容就是pull下来的内容，====和stashed changes之间的内容就是本地修改的内容。碰到这种情况，git也不知道哪行内容是需要的，所以要自行确定需要的内容。

解决完成之后，就可以正常的提交了。

方法出自：[git pull会把本地未提交修改覆盖吗？_百度知道 (baidu.com)](https://zhidao.baidu.com/question/1900051546382960220.html)
