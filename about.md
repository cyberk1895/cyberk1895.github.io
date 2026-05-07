---
layout: page
title: 关于
permalink: /about/
---

这是一个基于 Jekyll 和 GitHub Pages 的技术博客，适合用 Markdown 写技术类和代码类文档。

文章放在 `_posts` 目录，文件名遵循 `YYYY-MM-DD-title.md`，并在文件开头写 front matter：

```yaml
---
layout: post
title: "文章标题"
tags: [Jekyll, Ruby, Notes]
---
```

草稿放在 `_drafts` 目录，本地预览时使用 `bundle exec jekyll serve --drafts`。

正文支持 GitHub Flavored Markdown、代码块、表格和 Rouge 语法高亮。完整写作和部署步骤见仓库里的 `README.md`。
