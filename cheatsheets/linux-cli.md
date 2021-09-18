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

# Use current shell to run `SHELL_SCRIPT`
# e.g. source ~/.basrc
source [SHELL_SCRIPT]
```

## Command Execution

```bash
# 让 `CMD` 在后台运行, will print PID
# e.g.
[CMD] &

# 在 `CMD1` 成功后 (exit status == 0) 运行 `CMD2`
# 因为如果 `CMD1` 成功, `&&` 是 AND, 需要 run `CMD2` to evalaute
# the `&&` expression
[CMD1] && [CMD2]

# 在 `CMD1` 失败后 (exit status != 0) 运行 `CMD2`
# See https://unix.stackexchange.com/questions/37069/what-is-the-difference-between-and-when-chaining-commands
[CMD1] || [CMD2]

# STDIO redirect
# >>  : append to file
# >   : overwrite file
# 2>&1: redirect stderr to stdout
>>, >, 2>&1

# Launch a shell subprocess to run `CMD`
# And "return" output of `CMD` 
# e.g. List files in subdirectories
# ls `ls`
`CMD` and $(CMD)

```

## Navigation

```bash
# 当前路径 (print working directory)
pwd

# 改变当前路径 (change directory)
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
# 改变文件创建和修改时间
# 我通常用来创建新文件
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

# Set environmental variables for this shell and
# all child processes spawned from it
export GLOBAL_VAR=VALUE

# Match all
# e.g. list all C source code
# echo *.c
*

# Match zero or one character
# e.g. list files with `foo.` and end with one character extension
# echo foo.?
?

# Match one of the characters in []
# e.g. match all files with lowercase letters
# echo [a-z]*
[CHAR]
```

## Process Management

```bash
# Get process status
# Usually `ps -e` to show all processes
ps

# Show process information
top

# Show process information, but better
htop

# Kill process with process id `PID`
kill [PID]
```
