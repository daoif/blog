# Blog 项目 Agent 指南

## 项目概述

这是一个基于 GitHub Pages + Jekyll 的个人博客，文章以 Markdown 格式编写，自动转换为 HTML 页面。

## 目录结构

```
blog/
├── index.html           # 网站首页（文章列表入口）
├── README.md            # 项目说明
├── AGENT.md             # Agent 操作指南（本文件）
├── .gitignore           # Git 忽略规则
├── articles/            # 文章目录（.md 格式）
└── raw_materials/       # 原材料目录（已被 .gitignore 排除）
```

## 发布新文章流程

### 1. 准备原材料

将对话记录或素材保存到 `raw_materials/` 目录。

### 2. 生成文章

在 `articles/` 目录创建新的 `.md` 文件，文件名使用中文或英文均可。

### 3. 标注原材料

在原材料文件开头添加使用标注：

```markdown
> ⚠️ **原材料状态：已使用**
> 
> **生成产物**：[文章标题](../articles/文章文件名.md)
> 
> **生成时间**：YYYY-MM-DD

---
```

### 4. 更新 index.html

在 `<ul class="article-list">` 中添加新文章链接：

```html
<li>
    <a href="./articles/文章文件名.html">文章标题</a>
    <span class="date">YYYY-MM-DD</span>
</li>
```

> ⚠️ **注意**：链接使用 `.html` 后缀（Jekyll 会自动将 .md 转换为 .html）

### 5. 更新 README.md

在文章列表表格中添加新条目。

### 6. 提交并推送

```bash
git add -A
git commit -m "feat: 新增文章《文章标题》"
git push
```

### 7. 等待构建

GitHub Pages 会自动重新构建，通常 1-3 分钟后生效。

## 注意事项

- `raw_materials/` 目录不会同步到远端仓库
- 文章链接在 index.html 中使用 `.html` 后缀
- 文章文件在 articles/ 中使用 `.md` 后缀
