# hello-github

我的第一个 GitHub 仓库。用来熟悉 Git 和 GitHub 的完整流程：提交 → 分支 → Pull Request → 自动化检查。

## 这个仓库里有什么

| 文件 | 作用 |
|---|---|
| `README.md` | 项目说明，就是你现在看到的这个 |
| `.gitignore` | 告诉 Git 哪些文件不用追踪（日志、缓存、依赖等） |
| `LICENSE` | MIT 开源协议，允许别人自由使用你的代码 |
| `.github/workflows/ci.yml` | GitHub Actions 配置，每次推送会自动运行一次检查 |

## Git 命令速查

```bash
# 日常三连：改完代码后提交并推送
git status              # 看看改了哪些文件
git add .               # 把改动加入暂存区
git commit -m "说明"     # 提交到本地仓库
git push                # 推送到 GitHub

# 分支操作
git checkout -b feature-x   # 新建并切换到分支 feature-x
git switch main             # 切回主干
git branch                  # 查看所有分支

# 出错时
git diff                # 看具体改了什么
git log --oneline       # 看提交历史
git restore 文件名       # 撤销某个文件的改动
git reset --hard HEAD   # 撤销全部未提交的改动（慎用）
```

## 三个最常用但容易忘的概念

- **commit 只在本地生效**，必须 `push` 之后 GitHub 上才看得到
- **分支是平行世界**，新功能开新分支，确认没问题再合并回 `main`
- **Pull Request 是"请审一下"**，不是直接改代码，而是发起一次可被讨论、可被自动检查的合并请求

## 下一步

1. 给这个仓库加一个 `docs/` 文件夹，写点笔记
2. 开一个新分支练习 Pull Request
3. 给 README 加个徽章（badge），显示 Actions 是否通过

Made by zhangao880
