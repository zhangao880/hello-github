# Git 学习笔记

边用边记，按"什么时候会用到"来分类，不按命令字母排序。

## 一、每天都要用的四条

```bash
git status          # 我现在改了哪些文件？
git add .           # 把这些改动放进待提交区
git commit -m "说明" # 存档，写清楚这次改了什么
git push            # 同步到 GitHub
```

记住一句：**commit 是存本地，push 才是发网上**。忘了 push，GitHub 上就看不到。

## 二、想改坏了能退回去

```bash
git diff                 # 看具体改了哪几行
git restore 文件名        # 撤销某个文件的改动
git reset --hard HEAD    # 撤销全部未提交的改动（不可恢复，慎用）
git log --oneline        # 看历史存档记录
```

## 三、分支：给自己开个平行世界

```bash
git checkout -b feature-login   # 新建分支并切过去
git branch                      # 看看有哪些分支
git switch main                 # 切回主干
git merge feature-login         # 把分支的改动并回主干
```

什么时候该开分支：加新功能、改 bug、做实验。主干 `main` 保持随时可用。

## 四、Pull Request 是什么

不是"我直接改了"，而是"我改好了，请你看一下再合并"。一个 PR 里可以：

- 逐行评论代码
- 自动跑测试和检查（就是本仓库的 Actions）
- 讨论完再决定合不合并

## 五、我踩过的坑

1. **忘了配 `user.name` / `user.email`** → 提交会报错，用 `git config --global` 配一次就好
2. **把密钥提交上去了** → `.gitignore` 里一定要写 `.env`，密钥泄露要立刻去平台作废
3. **在 main 上直接改** → 养成开分支的习惯，改坏了不影响主线
4. **Windows 换行符警告** → 配 `core.autocrlf=true` 后不再提示

## 六、还没搞懂的

- `rebase` 和 `merge` 的区别
- 怎么把多个 commit 合并成一个（squash）
- `.git` 文件夹里到底存了什么
