# 白箱（shirohako）

白箱项目 monorepo。仓库本身不承载业务代码，通过 Git submodule 聚合前端与后端两个子仓库。

## 仓库结构

| 目录 | 说明 | 仓库 | 跟踪分支 |
|---|---|---|---|
| `shirohako-frontend` | 白箱前端 | `git@github.com:longlian-online/shirohako-frontend` | `main` |
| `shirohako-backend` | 白箱后端 | `git@github.com:longlian-online/shirohako-backend` | `main` |

## 使用

### 首次克隆

```bash
git clone --recurse-submodules git@github.com:longlian-online/shirohako.git
```

已克隆但缺少子模块时补拉：

```bash
git submodule update --init --recursive
```

### 日常操作

- 拉取全部最新代码：`git submodule update --remote --merge`
- 子仓库内正常切分支、提交、推送（各自独立仓库，跟踪各自 `main`）
- 在本仓库提交一次 submodule 指针变更，即可锁定子仓库版本

### 参考约定

结构与 `longlian-oa-dev` 保持一致：monorepo 仓库 + `*-frontend` / `*-backend` 两个 submodule，均跟踪 `main` 分支。
