# GitHub 上传说明

这个目录是已经清理的完整源码包，可以直接创建 Git 仓库并上传。建议仓库名：`wow-super-desktop`。

## 上传前包含的内容

- `apps/desktop`：Electron + React + TypeScript 正式桌面应用。
- `apps/prototype`：产品交互原型。
- `docs`：PRD、架构、技术手册和交付清单。
- `assets/reference`：视觉参考素材。
- `.github/workflows/desktop-ci.yml`：GitHub 自动检查配置。
- `README.md` 和 `.gitignore`：项目首页与上传排除规则。

## 已排除的本地内容

- `node_modules`、`dist`、`.vite`、`.next`、`.wrangler` 等依赖、构建结果和缓存。
- `.env` 和 API Key。
- SQLite 数据库、Electron `userData` 以及用户导入的私人文件。
- 旧 Git 历史，因此可以作为一个全新仓库上传。

## 方式一：使用 GitHub CLI

在这个目录打开终端，执行：

```bash
git init -b main
git add .
git commit -m "Initial release: wow super desktop"
gh repo create wow-super-desktop --private --source=. --remote=origin --push
```

如果希望公开仓库，把 `--private` 改为 `--public`。

## 方式二：使用 GitHub 网页

1. 在 GitHub 创建一个空仓库，不要勾选自动创建 README。
2. 在本目录执行：

```bash
git init -b main
git add .
git commit -m "Initial release: wow super desktop"
git remote add origin https://github.com/你的账号/wow-super-desktop.git
git push -u origin main
```

## 上传后本地运行

```bash
cd apps/desktop
npm install
npm run dev
```

