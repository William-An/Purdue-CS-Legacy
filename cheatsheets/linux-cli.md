# Linux CLI

Super basic commands for navigating general Linux distros like Ubuntu, also applies to MacOS as well in certain cases. References: manual of MacOS system.

- [Linux CLI](#linux-cli)
  - [General](#general)
  - [Command Execution](#command-execution)
  - [Navigation](#navigation)
  - [File Management](#file-management)
  - [Variables and Wildcards](#variables-and-wildcards)
  - [Process Management](#process-management)

## General

```bash
# 命令文档
# man cp
man [CMD]

# 以另外一名用户身份执行 `CMD`, 默认是以 superuser 身份
sudo [-u user] [CMD]

#
source
```

## Command Execution

```bash
# 让 `CMD` 在后台运行
# e.g.
[CMD] &

# Con
&&

# stdio redirect
>>, >, 2>1

#
`` and ${}

```

## Navigation

```bash
# 当前路径
pwd

# 改变当前路径
cd [FILE_PATH]

# 回到 $HOME 文件夹
cd ~ 

# 回到上一个路径，有些 shell 可能不支持
cd - 

# 回到上级目录
cd ..
```

## File Management

```bash
# 创建新文件
touch [FILE_NAME]

# 列出 `FILE_PATH` 下的文件, 
# -a: all files
# -l: detail info
ls [-al] [FILE_PATH]

# 复制文件/文件夹
# -r: copy recursively, if the `SRC_FILE` is a directory
cp [-r] [SRC_FILE] [DST_FILE]

# 远程通过 ssh 复制文件/文件夹
# e.g. 从 data 上复制 `~/file.c` 文件到本地, 假设用户名是 `john123`
#   scp john123@data.cs.purdue.edu:~/file.c .
scp [-r] [SRC_FILE] [DST_FILE]

# 移动文件
mv [SRC] [DST]

# 删除一个空目录, 如果不为空, 报错
rmdir [DIR_PATH]

# 删除文件/文件夹
# -r: remove file directory recursively
# -f: forced remove, 不要使用 `sudo` 执行
# e.g. 移除当前目录下所有以 `.out` 结尾的文件
#   rm *.out
rm [-rf] [FILE_PATH]
```

## Variables and Wildcards

Wildcard refs: [TLDP](https://tldp.org/LDP/GNU-Linux-Tools-Summary/html/x11655.htm)

```bash
# 当前 shell 环境下设置变量, 可以使用 $VAR_NAME 获得值
# e.g. 设置 `HELLO` 变量并打印它
#   HELLO="hello world"
#   echo $HELLO
#   `HELLO="I did changed"`
#   echo $HELLO
VAR_NAME=VAR_VALUE

#
# e.g.
export GLOBAL_VAR=VALUE

#
*

#
?

#
[]

#
{}
```

## Process Management

```bash
#
ps

#
top

#
htop

#
kill
```
