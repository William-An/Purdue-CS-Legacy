# git

[Git](https://git-scm.com/) 是一个开源代码版本管理器 (Version Control Software), 最初是由 Linus Torvald (Aka father of Linux) 开发来管理 Linux 的代码。无论是在校内还是工业界, Git 基本上是使用最广泛的代码管理工具, 与之相辅的 [GitHub](/tools/basic/github.md) 也是目前最大的代码仓库平台。

- [git](#git)
  - [Quick Quick Refs](#quick-quick-refs)
  - [Quick Refs](#quick-refs)
  - [Installation](#installation)
  - [`.gitignore`](#gitignore)
  - [Common usages](#common-usages)
  - [Pitfalls](#pitfalls)

## Quick Quick Refs

``` bash
git init
git clone [REMOTE_URL or LOCAL_PATH_TO_REPO]

git add [FILE_NAME]
git reset [FILE_NAME]
git commit -m "[COMMIT_MESSAGE]"
git push [REMOTE_REPO] [BRANCH]
git pull [REMOTE_REPO] [BRANCH]

git checkout -b [NEW_BRANCH_NAME]
git checkout [BRANCH_NAME or LOG_HASH]
git merge [BRANCH_NAME]

git status
git log
```

## Quick Refs

- `[]` 的内容需要你来填写
- `#` 以及后面文字为comments

``` bash
# Create empty repository
# 创建一个 git 仓库 
git init

# Clone a repository over remote or in local
# 克隆一个 git 仓库
git clone [REMOTE_URL or LOCAL_PATH_TO_REPO]

# Add files to be committed / staging
# 添加文件到git准备commit
git add [FILE_NAME]

# Undo adding
# 移除准备commit的文件
git reset [FILE_NAME]

# Commit staging files
# commit 现有添加的文件
git commit -m "[COMMIT_MESSAGE]"

# Redo commit
# 重置 commit
git commit --amend

# Push committed files to remote
# 推送commits到云端仓库
git push [REMOTE_REPO] [BRANCH]

# Pull commits from remote
# 从云端拉去更新
git pull [REMOTE_REPO] [BRANCH]

# Check out to another branch
# 开一个新的分支
git checkout -b [NEW_BRANCH_NAME]

# See commit log
# 查看commit log
git log

# See current directory status
# 查看当前目录下文件的状态: changed? staged? or newly created?
git status

# Change current working branch
# 更换当前分支
git checkout [BRANCH_NAME or LOG_HASH]

# Merge with other branch
# 把指定分支与当前分支合并
git merge [BRANCH_NAME]
```

## Installation

1. 如果你是 MacOS, Linux, 或者在 `data.cs.purdue.edu` 上, Git 已经提前安好了, 可以在 terminal 里直接用 `git version` 来查看版本号.
2. 如果你是 Windows 的话, 你需要下载 [`Git for Windows`](https://git-scm.com/download/win), download link: [here](https://git-scm.com/download/win).

## `.gitignore`

在你的 Git 仓库下添加一个 `.gitignore` 文件可以排除不需要添加进 repo 的文件, 例如 C 的 `*.out`, `*.o`, 和 Python 的 `*.pyc`, 常见格式如下:

``` git
# Intermediate files and builds
*.o
*.out
*.exe
*.elf
build/
build/*.out

# OS Related
.DS_Store
.DS_Store
```

你可以使用 `*` 作为通配符来匹配文件。同时可以指定排除一整个文件夹下的内容。需要注意的是, 如果你在 commit 后才将文件名放在 `.gitignore` 里，你会需要执行下列命令将文件从 Git 里面移除出来。

``` Bash
git rm --cache [FILE_NAME]
```

## Common usages

Git 通常被用来管理你的代码, 有如下几个使用案例:

1. 当你完成一项功能的时候，你可以使用 `git add` 与 `git commit` 来在 Git 里保存你的代码。
2. 当你写完代码后发现有 bug 想和之前的代码比对结果, 可以使用 `git log` 和 `git checkout [HASH]` 来暂时回滚到之前的版本。
3. 当你想和云端的仓库, 通常是 GitHub 同步时, 可以使用 `git pull` 和 `git push` 来拉取和推送更新。
4. 当你想在原有代码上完成一些新功能的时候, 可以用 `git checkout -b` 来创建一个副本分支 (copy), 同时在你原有分支上使用 `git merge` 来合并新功能。
5. 当你已经做了一些修改, 但是又想开个新的分支来放这些修改的时候, 可以使用 `git stash`, `git checkout -b`, 和 `git stash pop` 来将修改移到新的分支。
6. 当你不知道命令是干啥的时候, 可以使用 `git [CMD] --help` 来查看文档, 如 `git add --help`。

## Pitfalls

1. commit 的时候最好是对这个 commit 有一个理由才 commit, 比如对于 CS 作业, 你可以在写完第一题的时候 `git add . && git commit -m "Finish problem 1"`。
2. 尽量完成一个功能 commit 一次, 否则后面想回滚的时候会一次性把所有的功能全整没了。
