```markdown
---
name: xennic-documentation
description: مستندسازی خودکار تغییرات اساسی در Vault
version: 1.0.0
author: Xennic
tags: [documentation, automation, vault, xennic]
---

# مستندسازی خودکار تغییرات

## هدف
هر تغییر اساسی در سیستم به‌طور خودکار در `00_Meta/Integration/` مستند شود.

## چه زمانی مستند کن؟

✅ **مستند شود:**
- نصب/تغییر مدل (BGE-M3 → E5-large)
- تغییر Workflow (RAG-01 → RAG-02)
- تغییر Credential
- تغییر docker-compose
- حل مشکل اساسی (encoding فارسی)
- افزودن MCP Server
- افزودن اتوماسیون جدید

❌ **مستند نشود:**
- تغییرات جزئی (typo، رنگ)
- تغییرات موقت (test)
- preferences شخصی

## ساختار مستندات

00_Meta/Integration/
├── 0.1-baseline-snapshot.md
├── 0.2-open-notebook-security.md
├── 2.0-rag-shared-complete.md
├── 3.1-semantic-search-api.md
├── 3.3-hermes-mcp-n8n.md
├── 3.4-hermes-rag-integration.md
├── 4.0-content-separation.md
└── ...

text

## مراحل مستندسازی

### ۱. بررسی وجود مستندات
notes.search({ query: "{topic}", limit: 5 })

text

### ۲. اگر وجود دارد — بروزرسانی
- version را افزایش بده
- بخش جدید اضافه کن
- Changelog را بروزرسانی کن

### ۳. اگر وجود ندارد — ساخت
- از قالب `00_Meta/Templates/integration-template.md`
- نام‌گذاری: `{شماره}.{زیرشماره}-{عنوان}.md`
- لینک‌دهی به مستندات مرتبط

### ۴. تأیید از کاربر
"آیا این تغییر در `{path}` مستند شود؟"

## قالب مستندات

```markdown
---
id: META-INT-{id}
title: {title}
type: integration
status: done
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags: [integration, {tags}]
---

# {title}

## هدف
{goal}

## معماری
{architecture}

## پیکربندی
{config}

## تست
{test}

## نتایج
{results}

## چالش‌های حل‌شده
{challenges}

## لینک‌های مرتبط
{links}

