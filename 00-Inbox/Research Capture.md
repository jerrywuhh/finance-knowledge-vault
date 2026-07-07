---
tags: [workflow/capture, inbox, markdownload]
status: active
save_to: 00-Inbox/Downloaded
---
# Research Capture

## 保存位置
默认保存到：`00-Inbox/Downloaded`

## 适用资料
- 财经新闻
- 公司公告
- 财报文章
- Earnings Call Transcript
- 券商报告摘录
- Bloomberg / CNBC / WSJ / YouTube 等内容笔记

## 捕捉模板
```markdown
---
tags: [source/raw, inbox]
title:
source:
author:
published:
captured:
url:
status: downloaded
related_companies: []
related_concepts: []
initial_category:
next_action: clean
---
# {{title}}

## Source Info
- 标题：
- 来源：
- 作者：
- 发布时间：
- 抓取时间：
- 原始链接：

## Original Text

## Related Companies

## Related Concepts

## Initial Category

## Processing Status
- [ ] 已保存原文
- [ ] 已补来源和日期
- [ ] 已清理 Markdown
- [ ] 已建立内部链接
- [ ] 已移动到正式目录
```

## MarkDownload 工作流
网页 / 新闻 / 财报 / 文章  
→ MarkDownload  
→ `00-Inbox/Downloaded`  
→ [[Research Cleaner Prompt]]  
→ `00-Inbox/Cleaned`  
→ `02-Companies` / `03-Concepts` / `04-Research` / `05-Content`

## 规则
1. 原文先保存，不急着总结。
2. 来源、日期、链接必须保留。
3. 未读完、未分类、未清理的资料继续留在 Inbox。
4. 财经新闻和券商报告不能随意改写。
