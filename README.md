# nightflee.github.io

Personal blog. 纯静态站点，部署于 GitHub Pages。

## 文件结构

- `index.html` — 博客前台（首页 / 归档 / 文章 / 关于 / 搜索），运行时从 `posts.json` 动态加载文章
- `posts.json` — 全部文章数据（标题、分类、日期、标签、摘要、Markdown 正文）
- `admin.html` — 管理后台：在网页里新增 / 编辑 / 删除文章，通过 GitHub API 提交到本仓库
- `marked.min.js` — Markdown 渲染库（本地内置，无 CDN 依赖）

## 如何写文章

1. 访问 `https://nightflee.github.io/admin.html`（管理页不放在导航里，请记住地址）
2. 首次使用需创建一个 GitHub Token（详细步骤见管理页内的帮助说明）：
   - 打开 `github.com/settings/personal-access-tokens/new`
   - Repository access 只勾选 `nightflee/nightflee.github.io`
   - Permissions → Contents 设为 **Read and write**
3. 粘贴 Token 登录后即可新建 / 编辑 / 删除文章，「保存草稿」先存在本地，「发布到 GitHub」才真正提交
4. 提交后 GitHub Pages 自动重新部署，约 1 分钟后线上生效

## 安全说明

- Token 只保存在你自己浏览器的 localStorage 中，不写入仓库，任何人都无法通过网站修改文章
- 建议给 Token 设置过期时间，到期后在 GitHub 重新生成并重新登录一次
- `admin.html` 已设置 `noindex`，搜索引擎不会收录

## 本地预览

```bash
python -m http.server 8000
# 打开 http://localhost:8000
```
