# Tech Docs Blog

这是一个基于 Jekyll 的技术文档博客，适合写工程笔记、代码片段、问题复盘和架构文档。

## 技术栈

- Jekyll 静态站点生成
- Markdown / Kramdown 写作
- Liquid 模板
- Sass 样式
- Rouge 代码高亮
- GitHub Actions + GitHub Pages 部署
- jekyll-feed 和 jekyll-sitemap

## 本地预览

第一次运行先安装依赖：

```powershell
bundle install
```

启动本地服务：

```powershell
bundle exec jekyll serve
```

如果当前 PowerShell 还没有识别到 `bundle`，可以直接使用 RubyInstaller 的完整路径：

```powershell
C:\Ruby40-x64\bin\bundle.bat exec jekyll serve
```

打开：

```text
http://127.0.0.1:4000/
```

## 写文章

正式文章放在 `_posts` 目录，文件名必须使用这个格式：

```text
YYYY-MM-DD-title.md
```

例如：

```text
_posts/2026-05-07-jekyll-notes.md
```

文章开头要写 front matter：

```yaml
---
layout: post
title: "Jekyll 博客搭建笔记"
tags: [Jekyll, GitHub Pages, Notes]
---
```

正文直接写 Markdown：

````markdown
## 问题背景

记录问题、环境和目标。

## 代码示例

```js
function hello(name) {
  return `hello ${name}`;
}
```

## 结论

写下最终方案和后续事项。
````

建议：

- 文件名里的 `title` 用英文小写和短横线，避免中文 URL 编码过长。
- 一篇文章只写一个主题。
- 代码块写语言名，例如 `js`、`ts`、`python`、`bash`、`yaml`。
- 标签保持少量稳定，例如 `Jekyll`、`Ruby`、`Frontend`、`Architecture`、`Debug`。

## 写草稿

未完成的内容先放在 `_drafts` 目录。草稿文件不需要日期，例如：

```text
_drafts/architecture-note-template.md
```

预览草稿：

```powershell
bundle exec jekyll serve --drafts
```

草稿写完后，把文件移动到 `_posts`，并改成 `YYYY-MM-DD-title.md`。

## 插入图片

建议把图片放到：

```text
assets/images/
```

在 Markdown 中引用：

```markdown
![图片说明]({{ site.baseurl }}/assets/images/example.png)
```

## 部署到 GitHub Pages

这个项目已经包含 GitHub Actions workflow：

```text
.github/workflows/pages.yml
```

部署步骤：

1. 在 GitHub 新建一个仓库。
2. 仓库名可以是 `makeBlog`，发布后地址通常是 `https://你的用户名.github.io/makeBlog/`。
3. 如果你想使用根域名地址 `https://你的用户名.github.io/`，仓库名必须是 `你的用户名.github.io`。
4. 新仓库不要勾选初始化 README、`.gitignore` 或 License，避免和本地文件冲突。
5. 在本地项目目录执行：

```powershell
git init
git branch -M main
git add .
git commit -m "Initial Jekyll blog"
git remote add origin https://github.com/你的用户名/仓库名.git
git push -u origin main
```

6. 打开 GitHub 仓库页面，进入 `Settings -> Pages`。
7. 在 `Build and deployment` 里把 `Source` 设为 `GitHub Actions`。
8. 进入 `Actions` 页面，等待 `Build and deploy Jekyll site` 成功。
9. 回到 `Settings -> Pages`，点击 `Visit site`。

之后每次发布新文章：

```powershell
git add .
git commit -m "Add new post"
git push
```

GitHub Actions 会自动重新构建和发布。

## 常见问题

如果浏览器显示 `127.0.0.1 拒绝建立连接`，说明本地 Jekyll 服务没有运行。重新执行：

```powershell
bundle exec jekyll serve
```

如果 `bundle` 无法识别，关闭 PowerShell 后重新打开；仍然不行就使用完整路径：

```powershell
C:\Ruby40-x64\bin\bundle.bat exec jekyll serve
```
