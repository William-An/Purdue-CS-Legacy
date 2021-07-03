# ssh

SSH (secure shell protocol) 是一个用来和远程主机建立安全网络链接的协议。通常用来远程登录到主机上执行命令，编译运行CS作业。加密方式是公私钥加密，像RSA 就是一种公私钥加密算法。

## Quick Refs

```bash
# ssh 登陆
ssh [USERNAME]@[HOST]

# 如果你的 Purdue career account 是 john123, 想要登陆 data.cs.purdue.edu
ssh john123@data.cs.purdue.edu

# 建立 ssh 密钥对
ssh-keygen -b [bits] -C [comment] -t [TYPE]

# 如4096位的 RSA 加密
ssh-keygen -b 4096 -C "Sample ssh key" -t rsa

# 将 ssh 公钥放到远程主机上，这样下次登陆就不需要输入密码
ssh-copy-id [USERNAME]@[HOST]

# 将 ssh key 放到 data 上
ssh-copy-id john123@data.cs.purdue.edu
```

## Common usages

### 远程主机连接

Purdue CS 里最常用的就是通过 ssh 远程连接到 data 主机上跑程序:

```bash
ssh [USERNAME]@data.cs.purdue.edu
```

如果你用 `ssh-keygen` 和 `ssh-copy-id` 建立了公私钥对并放到了 data 后，以后从你当前电脑 ssh 登陆 data 就不需要输入密码:

```bash
# 创建一个 ssh 密钥对
ssh-keygen -b 4096 -C "Purdue SSH key" -t rsa

# 添加 ssh 公钥到你的 home directory 里
ssh-copy-id [USERNAME]@data.cs.purdue.edu

# 直接 ssh 登陆 data
ssh [USERNAME]@data.cs.purdue.edu
```

### GitHub clone repo

当你在你的 GitHub 设置页面的 [SSH and GPG keys](https://github.com/settings/keys) tab 里添加完你的 **ssh 公钥** 后，你可以直接用 ssh clone 代码仓库，从而不需要输密码。

## Others

其他一些和 ssh 相关的工具

### `scp`

从远程主机复制 (`cp`) 文件， 用 `man scp` 查看命令文档

### `sftp`

基于 ssh 的 ftp (file transfer protocol)，可以让你本地与远程主机交换数据，可以看看 [Cyberduck App](https://cyberduck.io/)，一个开源免费的 FTP，SFTP 客户端程序。
