# How to push local file to Github by Git

1. 下载安装Git

2. 在本地创建ssh key

   ``` shell
   $ ssh -keygen -t rsa -C "your_email@youremail.com"
   ```

3. 在用户根目录下的`.ssh`文件夹会生成密钥。打开`id_rsa.pub`，复制里面的key（全部复制）

4. 在Github上的Settings-->SSH and GPG keys-->New SSH key，将上一步复制的密钥粘贴进去。

5. 验证是否生效

   ``` shell
   $ ssh -T git@github.com
   Hi suyesean! You've successfully authenticated, but GitHub does not provide shell access.
   ```

6. 配置用户名和邮箱

   ``` shell
   $ git config --global user.name "your name"
   $ git config --global user.email "your_email@youremail.com"
   ```

7. Git和Github协作2种方式

   - 克隆远端

     直接在本地克隆远端的仓库

     ``` shell
     $ git clone git@github.com:suyesean/HowToGitHub.git
     ```

   - 本地直接推到远端

     本地创建文件夹，然后git一系列操作

     ``` shell
     $ git init
     $ git add hello.md
     $ git commit -m "first commit"
     # bridge local file to remote repository only used when fisrt.
     $ git remote add origin git@github.com:suyesean/helloGitHub.git 
     $ git push -u origin master
     ```

8. 参考：

   [Step1~6][1] 参考

   [1]: https://www.runoob.com/w3cnote/git-guide.html