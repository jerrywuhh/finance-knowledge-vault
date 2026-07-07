---
tags: [github, sync, setup]
status: blocked-auth
repo: https://github.com/jerrywuhh/-.git
---
# GitHub Sync Setup

## 当前状态
- 本地 Git：已初始化
- 本地分支：`main`
- Remote：`origin https://github.com/jerrywuhh/-.git`
- 本地提交：已完成
- Pull：未完成，原因是命令行 GitHub 未登录
- Push：未完成，原因是命令行 GitHub 未登录
- GitHub CLI：未安装
- Homebrew：未安装

## 已验证结果
命令行访问 GitHub 时返回：`could not read Username for 'https://github.com': Device not configured`

这说明 GitHub 仓库可能是私有仓库，或者本机命令行还没有配置 GitHub 凭据。

## 继续同步的最简单路线：GitHub Desktop
1. 安装并打开 GitHub Desktop。
2. 登录 GitHub 账号 `jerrywuhh`。
3. 选择 `File -> Add Local Repository`。
4. 选择本地文件夹：`/Users/tangjingyue/Desktop/Finance-Knowledge`。
5. 确认 remote 是：`https://github.com/jerrywuhh/-.git`。
6. 点击 Fetch / Pull。
7. 如果远程仓库是空的，点击 Push origin。
8. 如果提示远程已有文件，先 Pull，再处理冲突。

## 命令行路线
如果之后安装并登录 GitHub CLI，可执行：

```bash
gh auth login
cd /Users/tangjingyue/Desktop/Finance-Knowledge
git pull origin main --allow-unrelated-histories
git push -u origin main
```

如果不安装 GitHub CLI，也可以使用 GitHub Personal Access Token 作为 HTTPS 凭据。

## 当前本地 Git 命令
```bash
cd /Users/tangjingyue/Desktop/Finance-Knowledge
git status
git log --oneline -1
git remote -v
```

## Obsidian Git 插件建议
当前没有检测到 Obsidian Git 社区插件。安装后建议：
- Vault backup interval：10-30 分钟
- Auto pull interval：10-30 分钟
- Commit message：`vault backup: {{date}} {{time}}`
- Pull before push：开启
- Disable push：关闭，等首次 push 成功后再自动化
- 注意：如果 GitHub 凭据没配好，插件也无法 push。
