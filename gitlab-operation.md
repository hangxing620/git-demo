## gitlab fork 同步

gitlab fork 别人的项目之后需要更新，没有界面操作，比较麻烦，只能通过命令行

### 查看项目远程仓库的配置

fork出来，没有源项目的地址信息，只有自己fork项目的地址

```shell
git remote -v

# origin git@gitlab.com:Evan880/aws.git (fecth)
# origin git@gitlab.com:Evan880/aws.git (push)
```

### 添加源项目的地址

```shell
git remote add upstream URL

# git remote add upstream git@gitlab.com:fell/aws.git
```

### 查看是否添加成功

```shell
git remote  -v

# origin git@gitlab.com:Evan880/aws.git (fecth)
# origin git@gitlab.com:Evan880/aws.git (push)
# upstream git@gitlab.com:fell/aws.git (fetch)
# upstream git@gitlab.com:fell/aws.git (push)
```

## 获取源项目的更新

```shell
git fetch upstream
```

## 合并源项目的同步

```shell
git merge upstream/master
```

[gitlab fork 同步操作1](C9205A2EE5C16401D7F241886AB32957.png)

[gitlab fork 同步操作2](427CC0DD13238DE15A66052CC221B750.png)
