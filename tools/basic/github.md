# github

[GitHub](https://github.com/) 是基于 [Git](/tools/basic/git.md) 的一个云端代码托管平台 (就是用来存你的代码用的)。使用 GitHub 可以更加轻松的管理/协作你的代码, 同时也是可以是你个人的 project profolio, 如[我的GitHub主页](https://github.com/William-An/)。除了代码管理以外, GitHub 可以用来托管静态网页, 像本文档就是使用 [GitHub Pages](https://pages.github.com/) 部署的。同时你也可以使用 [GitHub Action](https://github.com/features/actions) 来尝试 CI/CD 和自动代码部署, 例如使用 [GitHub Action 来自动测试网站代码并推送到服务器上](https://github.com/PikaCourse/homiehomie/blob/main/.github/workflows/dev-ci.yml)。

但是对于 Purdue CS 来说, GitHub 最大的用处就是可以用来同步你本地和 data 上的代码。但是如果你想 aim higher, 做一些课外项目, GitHub 是十分有用的。

## Common usages

### Pull Request

Pull Request（PR） 是一项 GitHub 的功能，可以让你在云端从另一分支合并到主分支，通常用途如下：

1. 你先是在本地 git 创建一个新的分支来实现一些新功能，如 `UI_V0.2`
2. 实现完以后，你可以 `git push` 到云端
3. 在云端 GitHub 你可以创建一个 pull request 来合并到 `main` 分支上

通常 Pull Request 被用于网站或移动应用的快速 feature development，同时也可以作为对 GitHub 上开源项目的补充。

### Fork

Fork 可以让你在 GitHub 上复制其他人的 repo 到你名下。Fork 会保留之前所有的 commit history 已经 branches。通常用于你想开发一个现用 repo 没有的功能时使用。

### GitHub Pages

通过 [Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll) 在 GitHub repo 里部署静态网页。你可以用这个功能来像本文档一样创建文档软件或者为你的 repo 添加一个好看的文档介绍。如果你想用 GitHub Pages 的话，在 repo setting 中启动后创建 `index.md` 或者 `index.html` 就可以自动生成网站。

### Branch

Branch 可以让你管理不同版本的代码，GitHub 的 branch 和 Git 的 branch/分支是一个概念。通常的软件开发会有 `master/main` 和 `dev` branches。`master/main` 是主分支，存放最稳定的代码。 `dev` 是开发分支，当 `dev` 上的代码测试完后会被 merge 进 `master/main`。如果需要开发新功能的话，可以从 `dev` 上 `git checkout` 一个 feature 分支出来，如我想为我的 iOS程序 开发新的 UI, 可以在 `dev` 上用 `git checkout -b new_UI`。
