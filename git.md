# git用法

#### 1. git的基本命令

```
(1) git init => 初始化仓库
(2) git add . => 把代码从工作区提交到暂存区
(3) git commit -m '提交日志' => 把暂存区的代码提交到仓库区
(4) git status => 查看文件的状态(红色的工作区/绿色的在暂存区)
(5) git log => 查看提交的日志   git reflog
(6) git diff => 查看工作区与暂存区的不同
	git diff --cached => 查看暂存区和仓库区的不同
	git diff HEAD => 查看工作区和仓库区的不同
(7)	git reset --hard 版本号 => 回退版本(慎用)
(8) 输入命令之前,需要设置
	git config --global user.name '用户名'
	git config --global user.email '邮箱'
```

#### 2. git忽视文件

```
.gitignore => 想要忽视谁，往这个文件加就行了
```

#### 3. git分支操作

```
(1) git checkout 分支名 => 切换分支
(2) git checkout -b 分支名 => 创建并切换分支
(3) git branch => 查看分支
(4) git branch -d 分支名 => 删除分支
(5) git merge 分支名 =>合并分支
注: 分支合并时可能会发生冲突,需要手动修复
```

#### 4. git远程操作

```
(1) git clone 远程仓库地址 本地的名字  => 克隆代码
(2) git push origin master => 提交代码
注: 以后git push前记得git pull
(3) get pull => 拉取更新
(4) git remote add 别名  远程仓库地址   => 添加别名
(5) git remote remove 别名 => 删除别名
(6) ssh免密码登录
```