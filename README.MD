# Git 版本控制工具 速查表

###### 版本：后悔药，每一个版本的就是一个后悔药
###### 版本控制工具：一个控制后悔药并且还能在后悔药上玩出点新花样的工具
###### 速查表： 懂了Git的基本原理，记不住命令，过来查一下 👇
###### <a href="https://git-scm.com/book/zh/v2">Git官方文档点这里</a>

## 下载 安装 配置
- https://git-scm.com 下载git并安装
- git config --global user.name "<姓名>" 设置提交者姓名。
- git config --global user.email "<邮箱>" 设置提交者邮箱。
 
## 创建仓库
###### 仓库： 项目
- **git init [目录名]：**  在指定目录创建仓库，如果没有指定目录名将在当前目录创建仓库。
- **git clone <远程仓库地址> [目录名]：** 从指定地址克隆仓库，若不指定目录名将默认创建与远程同名目录。

## 基本指令

#### git status 查看仓库状态
* _No commits yet_ 还没提交
* _Untracked file_ 存在未被追踪的文件 _modified_ 存在未被追踪的已经修改的文件
* _Changes to be committed_ 更改已被提交
* _Nothing to commit,working tree clean._ 已无可提交的文件

#### git add <目录名|文件名> 添加跟踪或添加到暂存区：
* git add . 或 git add * 或 git add -A 将所有修改添加到暂存区或添加追踪

#### git commit 提交
* git commit -m "<提交注释>" 提交并写提交注释
* git commit 提交，出现默认编辑器（如:vim）写入提交注释
* git commit -a 直接将修改后的文件提交（跳过了add过程）

#### git branch 分支
- git branch [分支] 有分支：创建分支，无分支：列出所有分支。
- git checkout <分支> 切换至分支。
- git checkout -b <分支> 创建并切换至分支分支。
- git merge <分支> 将分支与当前分支合并。

#### git log 查看git日志
- git log [--oneline] [--all] 查看提交历史。
- git log --oneline 打印为单行log。
- git log --all 打印所有记录（忽略HEAD的位置）
- git log --graph 打印示意图（忽略HEAD的位置）
- git log -p 在尾部追加具体修改内容

#### git diff 对比
- git diff 比对当前内容和暂存区内容
- git diff HEAD 比对当前内容和最近一次提交
- git diff HEAD^ 比对当前内容和倒数第二次提交
- git diff HEAD^ HEAD 比对最近两次提交

#### git checkout 切换版本或分支
###### ID 一般7位即可定位一个历史记录
- git checkout "ID" 切换到该ID的版本
- git checkout - 回到“上次”节点，类似于浏览器返回按钮
- git checkout <分支> 切换至分支
- git checkout -b <分支> 创建并切换至分支分支
- git checkout <标签名> 跳转到相应标签

#### git merge 合并分支
- git merge <要合并到当前分支的分支名>

#### git tag 添加标签
###### tag 一般为版本信息 如 v1.0.0
- git tag 查看所有tag
- git tag -a <标签名> -m "<描述信息>" [ ID ] ID没有时，给当前版本添加tag，否则给指定版本添加tag
- git show <标签名> 查看相应标签的信息
- git checkout <标签名> 跳转到相应标签

#### 远程
###### git pull === git fetch && git merge
- git pull 拉取远程仓库，到committed阶段
- git fetch 拉取远程仓库，到modified阶段
- git push <远程仓库> <分支> 推送至远程仓库
- git remote add origin <仓库地址> 新增远程仓库origin
- git remote set-url origin <仓库地址> 修改远程仓库origin

## 基本状态
- **modified----> 已修改**
	-  变动committed文件后的状态
- **staged ------> 已暂存**
	- add 后的文件状态
- **committed -> 已提交**
	- commit后的文件状态 


