---
title: 【Markdown】Typora导出pdf分页的两种方法
tag: [Markdown, CN]
thumbnail: https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=4113329853,987323438&fm=11&gp=0.jpg
category: IT
---

## 自动分页符

有时您可能需要导出为PDF，并在顶层标题上使用分页符。 打开主题文件夹，然后编辑要包含的主题的css
```css
@media print {
  h1 {
    page-break-before: always;
  }
  h1:first-of-type {
    page-break-before: avoid;
  }
}
```
现在，在导出时，将在每个h1元素（第一个元素除外）之前创建一个新页面。

## 强制分页符（方便）
要在文档上插入分页`<div style="page-break-after: always;"></div>`符，可以在书写时尝试输入HTML 。