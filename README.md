# Vue 3 + TypeScript + Vite

This template should help get you started developing with Vue 3 and TypeScript in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Project Info
- Vite 7
- Vue 3.5
- TypeScript
- pnpm

## Git 仓库管理和开发流程指南

### 一、初始化本地仓库

1. 创建 `.gitignore` 文件，包含以下内容：
```bash
# Dependencies
node_modules
.DS_Store
dist
dist-ssr
coverage
*.local

# Editor directories and files
.vscode/*
!.vscode/extensions.json
!.vscode/settings.json
.idea
*.suo
*.ntvs*
*.njsproj
*.sln
*.sw?

# Logs
logs
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*
pnpm-debug.log*

# Environment variables
.env
.env.*
!.env.example
```

2. 初始化仓库命令：
```bash
git init
git add .
git commit -m "feat: 初始化项目"
```

### 二、SSH 配置

1. 生成 SSH 密钥：
```bash
ssh-keygen -t ed25519 -C "your.email@example.com" -f ~/.ssh/github_ed25519 -N ""
```

2. 配置 SSH：
```bash
# ~/.ssh/config
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/github_ed25519
```

3. GitHub 配置：
- 添加公钥到 GitHub (Settings -> SSH and GPG keys)
- 测试连接：`ssh -T git@github.com`

### 三、远程仓库设置

```bash
# 添加远程仓库
git remote add origin git@github.com:username/repo-name.git

# 推送代码
git push -u origin master
```

### 四、分支管理

1. 分支结构：
- master: 主分支，用于生产环境
- develop: 开发分支，用于开发环境
- feature/*: 功能分支
- bugfix/*: 问题修复
- hotfix/*: 紧急修复
- release/*: 发布分支

2. 创建开发分支：
```bash
git checkout -b develop
git push -u origin develop
```

3. 分支保护设置（GitHub）：
- Settings -> Branches -> Add branch protection rule
- 保护规则：
  - 需要 Pull Request
  - 需要代码审核
  - 包含管理员
  - 禁止强制推送

### 五、开发工作流程

1. 功能开发：
```bash
# 创建功能分支
git checkout develop
git pull
git checkout -b feature/feature-name

# 提交代码
git add .
git commit -m "feat: 添加新功能"
git push -u origin feature/feature-name
```

2. 代码合并流程：
- feature -> develop: 功能开发完成
- develop -> master: 版本发布

3. Pull Request 流程：
- 创建 PR
- 代码审核
- 解决冲突
- 合并代码

### 六、提交规范

```bash
# 提交格式
<type>: <description>

# 类型说明：
- feat: 新功能
- fix: 修复问题
- docs: 文档变更
- style: 代码格式调整
- refactor: 重构代码
- test: 测试相关
- chore: 构建过程或辅助工具的变动
```

### 七、注意事项

1. 禁止直接在 master 分支开发
2. 定期同步 develop 代码到功能分支
3. 提交前进行代码测试
4. 保持提交信息规范
5. 及时处理代码冲突
6. 重要修改必须通过 PR 和代码审核