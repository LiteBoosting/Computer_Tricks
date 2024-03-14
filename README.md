# Git Tricks
## Scenarios
### 看到Github上面一个不错的projcect，然后想自己玩玩儿，而不是去作为贡献者（贡献者需要pull request）
1. 直接过去fork，然后保存为你自己的某一个repository
2. 用Terminal直接去 `git clone <repository>`
3. 用IDE去打开，然后选择"open project"

## Basic Commands

| Git Command      | Description |
| ----------- | ----------- |
| `git init`      | creates a new local repository |
| `git clone <repository>`| — clones an existing repository |
| `git status`| lists changed files in your working directory |
|`git add .` | — adds all current changes to the next commit |
|`git commit` | — commits previously staged files |
|`git branch <new-branch>` | — creates a new branch based on your current HEAD |
|`git checkout <branch>` | — switches to a different HEAD branch |
|`git push <remote> <branch>` | — publishes local changes on a remote repository |
|`git pull <remote> <branch>` | — downloads changes from a remote repository and integrates them into HEAD |
|`git merge <branch>` | — merges the specific branch into your current HEAD.Paragraph |
| `touch qwen_vl_max_testing.py` | create a new file without opening it |


1. 找到.git -> 类似：https://github.com/LiteBoosting/LLM_testing.git
2. 创建一个本地目录 `mkdir ./testing`
3. `git init`
4. `git clone https://github.com/LiteBoosting/LLM_testing.git`（注意有效的git地址一定是`xxx.git`）
5. `git pull https://github.com/LiteBoosting/LLM_testing.git main`
6. `git add .`
7. `git commit -m "xxxx"`
8. `git push -u https://github.com/LiteBoosting/LLM_testing.git main`
9. `git status`
10. `git checkout main` （在`main`这个地方checkout）
11. `git branch` （查看当前有哪些分支 - Github允许代码有分支，Facebook可不允许，这是两者逻辑的重要区别）

## FAQ
(1)
Git pull error: RPC failed; curl 16 Error in the HTTP2 framing layer. fatal: expected flush after ref listing
```
$ git pull 'https://gitlab....'
error: RPC failed; curl 16 Error in the HTTP2 framing layer
fatal: expected flush after ref listing
```

Try to force git to use HTTP 1.1 by setting git config like this

`git config --global http.version HTTP/1.1`
then pull

if you want to set it back to HTTP2 you can do the same

`git config --global http.version HTTP/2`
