# Git教程
## 创建Git密钥：
### 1、生成密钥：
右键–>Git Bash Here：先输入ssh-keygen –t rsa –C "邮箱地址",注意ssh-keygen之间是没有空格的,其他的之间是有空格的，邮箱地址是咱们在注册GitHub的时候用的邮箱。

生成的密钥在这里：C:\Users\Administrator\.ssh

### 2、将id_rsa.pub用记事本打开，复制里面全部的内容，放在GitHub的SSH Keys上：
右上头像箭头->Settings->左侧SSH and GPG keys,New SSH key,粘贴，Add GPG key

### 3、ssh –T git@github.com 验证设置是否成功：
Administrator@FEZLIN8TDST7KOF MINGW64 /githere
$ ssh -T git@github.com
The authenticity of host 'github.com (13.250.177.223)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no)? yes

这里回复一个yes,而！不！是！习！惯！性！回！车！！
Warning: Permanently added 'github.com,13.250.177.223' (RSA) to the list of known hosts.
Hi Xiaobai0419! You've successfully authenticated, but GitHub does not provide shell access.

这时是在c盘.ssh目录下多生成了一个known_host文件，再次尝试命令，成功：
Administrator@FEZLIN8TDST7KOF MINGW64 /githere
$ ssh -T git@github.com
Hi Xiaobai0419! You've successfully authenticated, but GitHub does not provide shell access.

IDEA进行Github账号登录时，使用https（用户名密码）或ssh协议（密钥）如https://github.com才能顺利登录，http是无法成功的。

### 4.提交项目：
- 4.1、切换到项目根目录，创建本地仓库（.git隐藏目录中写入信息，如果此前有这个目录，需先整个删除）：
  
    ```$ git init```

- 4.2、将目录下所有文件添加到本地仓库：
    ```$ git add .```

- 4.3、提交到本地仓库，添加注释：  
  
    ```$ git commit -m 'dubbo first commit'```

- 4.4、添加远程仓库地址（需要先在GitHub上建好，复制地址到这里），命名为origin：  

    ```$ git remote add origin https://github.com/Xiaobai0419/minexiaobai0419.git```

- 4.5、推传到远程仓库：  
  
    ```$ git push -u origin master```

Username for 'https://github.com': Xiaobai0419

需要输入GitHub注册的用户名、密码后确认

- 4.6、如果项目已存在于远程仓库（仓库不为空，或其他人上传、更新了仓库），要先pull更新，尤其是有在其他点推传更新的时候：   
  
    ```$ git pull --rebase origin master```

尤其是在远程新建仓库中创建了README.MD文件的时候，一定要先pull同步远程文件过来，再push,否则就会上传失败！！
- 4.7、此后可直接在配置了同一个Git.exe的IDEA中添加、提交、push到远程仓库。
- 4.8.合并分支
Fork分支和主分支同步，并提交到fork分支（自己的远程仓库，必须是先在网站上fork一份原作者分支到自己的远程仓库，然后git clone自己fork的远程仓库！）：

https://blog.csdn.net/wangww631/article/details/78392734

https://www.jianshu.com/p/633ae5c491f5

分支创建、合并原理和编辑冲突、提交（也是提交到自己的远程仓库）：

https://www.cnblogs.com/wangmingshun/p/5425150.html

GitHub请求合并分支申请（到网站申请，需要经过原作者同意，编辑冲突，合并到人家的主分支）：

https://www.jianshu.com/p/43d060a082cb

GitLab的合并分支申请：

https://blog.csdn.net/zangxueyuan88/article/details/81099984

9.可视化工具SourceTree的使用
安装时按步骤先到其网站建立一个自己账号，完成安装。安装后可以关联多个远程仓库，包括自己建立账号的仓库，或者软件支持的GitHub、GitLab等上面自己的账号。

将开源项目先fork到自己的远程仓库，然后使用该工具从自己的远程仓库地址clone到本地的一个仓库（建立好的文件夹），按文中建立各种分支，停留在某个分支上，使用IDE修改本地仓库源码，或手动增减、修改文件，停留的分支自动感应变化，再按文中提示进行提交、编辑冲突、合并分支、推送到远程仓库，其中推送到远程仓库需要提供你自己远程仓库的用户名、密码，确认后成功推送。

https://www.cnblogs.com/tian-xie/p/6264104.html

https://blog.csdn.net/wjy1990831/article/details/80417820

https://www.jianshu.com/p/be9f0484af9d

10.IDEA直接在GitHub远程创建仓库，提交并推送
a.配置好Git,GitHub个人账号、密码

b.选中项目，使用VCS->Import into Version Control->Share Project on GitHub,这样只能在远程创建一个同名的空仓库：



c.这时项目右键出现Git,选择add,commit你想提交的部分

d.这时使用VCS->Git->push是会推送失败的，因为IDEA默认给配置的远程仓库地址是错误的！需要在VCS->Git->Remotes中改为GitHub上该仓库复制地址：



 

修改成正确的GitHub远程仓库地址之后，使用push即可远程推送代码成功。

 

e.要使用IDEA从远程GitHub库引进一个项目，需要使用VCS->Git->Clone,添加远程库Git地址，修改后可按上述方法直接提交，推送到远程库。

11.怎样在GitHub更新fork到自己仓库的项目
参照https://blog.csdn.net/zhongzunfa/article/details/80344585

注意点击compare across forks时，base fork选填自己fork的项目，head fork选填原作者主分支项目，这样才能操作成功！！





# 命令行

- 查看目录下的文件```dir```
- 创建文件夹```md filesname```
- 创建文件 ```cd.>filename.md```