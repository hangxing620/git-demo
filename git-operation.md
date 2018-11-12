# git协同操作的步骤

仓库管理员: A
fork开发者: B

## 初始化git仓库

使用github或者gitlab初始化源仓库

## A 克隆项目下来，提交develop分支

```shell
# 创建之后，有master分支
git clone https://github.com/hangxing620/git-demo.git
```

创建`develop`分支

```shell
git brance develop
```

提交develop分支

```
git push origin develop
```

## B fork 项目，进行开发

B fork项目，并克隆项目到本地

```shell
git clone https://github.com/evan880/git-demo.git

cd git-demo
```

切换到开发分支，并进行构建功能分支进行开发

```shell
# 切换到开发分支
git checkout develop

# 分出一个功能性分支
git checkout -b feature-readme

# 假如git-operation.md是我们要开发的功能
# 创建git-operation.md文件
touch git-operation.md

# 编辑git-operation.md
vim git-operation.md

# 编辑好了git-operation.md文件
# 注释开发的功能，并提交
git add .

git commit -m "finish feature-readme"

# 回到develop分支
git checkout develop

# 把做好的功能合并到develop分支
# 命令行的合并需要关闭一个文件，使用q退出文件
git merge --no-ff feature-readme

# 删除功能性分支
git brance -d feature-readmd

# 把develop提交到自己的远程仓库
git push origin develop
```

## 开发者B 向管理员A提交pull request

在github的项目上面，可以看到`Compare & pull request`按钮

提交pull request

## 管理员A 测试、合并

创建一个新的测试分支，作为pull分支
```shell
# 先进入管理员A的develop分支
git checkout develop
# 从develop分支中分出一个创建evan880-develop测试分支
git checkout -b evan880-develop

# pull 开发者B的 develop 分支
git pull https://github.com/evan880/git-demo.git develop

# 测试通过之后，合并到源仓库的develop中
git checkout develop

git merge --no-ff evan880-develop

git push origin develop
```




