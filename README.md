# git-demo

git 测试项目

## 设置git全局的用户名和邮箱

```shell
git config --global user.name "Evan"

git config --global user.email "13539886724@163.com"

git config user.name # Evan

git config user.email # 13539886724@163.com
```

## 生成ssh key

- -t 指定密钥类型，默认是rsa，可以省略
- -C 设置注释文字，比如邮箱
- -f 指定密钥文件存储文件名，默认的名称id_rsa

不要设置密码，按Enter跳过

```shell
ssh-keygen -t rsa -C "you_email@example.com" -f id_rsa_github

# 如果是自定义密钥的文件名，需添加如下操作 
ssh-add ~/.ssh/id_rsa_github

```

## 设置不同的ssh针对不同git服务器

在~/.ssh/文件夹下新增config文件，设置不同git服务器的ssh

```shell
touch config # 新增config文件

vim config # 编辑config文件
```

```text
# config 文件

# github
Host github.com
HostName github.com
PreferredAuthentications publickey
IndentityFile ~/.ssh/id_rsa_github

```

## git 协同开发

[git协同开发](git-operation.md)

## gitlab fork 同步

[gitlab fork 同步操作](gitlab-operation.md)
