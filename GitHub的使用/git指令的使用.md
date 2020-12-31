# git指令

1. 初始化仓库

   `git init`

2. 查看状态

   `git status`

3. 添加待上传的文件

   `git add "文件名"`：添加指定文件

   `git add -A`：添加目录下的所有文件

4. 提交

   `git commit "更新描述"`

5. 查看状态改变的文件

   `git diff`

6. 查看代码版本

   `git reflog`

7. 版本回退

   `git reset --hard 版本号前7位`

8. 删除未add文件

   `git clean -xf`


# 本地git与GitHub的关联方法

### 本地配置用户名和邮箱

1. `git config --global user.name "GitHub用户名"`

2. `git config --global user.email "GitHub注册邮箱"`

### 生成ssh key

1. 生成ssh key：`ssh-keygen -t -rsa -C "邮箱"`
2. 复制ssh key：`clip <~/.ssh/id_esa.pub`  会自动复制ssh key

### 连接GitHub

1. 在GitHub的setting的ssh key中新建，并输入刚刚复制的ssh key
2. 测试连接：`ssh -T git@github.com`
3. 在GitHub上新建一个仓库，并复制仓库的ssh地址
4. 运行`git remote add origin ssh地址`

### 上传文件

> 若在GitHub上对文件进行了修改，可能会导致push的时候被GitHub拒绝
>
> 可以通过执行`git pull origin master`解决，这条指令会把GitHub上的内容拉取到本地

1. 执行指令：`git push -u origin master` 或者 `git push` 可以直接把本地刚刚commit的内容提交到GitHub上。

### 下载别人的代码的指令

`git clone SSH地址`

