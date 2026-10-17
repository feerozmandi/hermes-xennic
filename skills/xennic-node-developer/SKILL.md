---
name: xennic-node-developer
description: توسعه نودهای Obsidian Xennic با ساختار node-template.md
version: 1.0.0
author: Xennic
tags: [obsidian, node, development, xennic]
---

# توسعه نود Obsidian Xennic

## هدف
ساخت یا بروزرسانی نودهای Obsidian با ساختار `00_Meta/Templates/node-template.md`.

## Vault
- **مسیر:** `F:\ahmad\obsidian\ZNNY-Xennic-Vault`
- **قالب:** `00_Meta/Templates/node-template.md`

## ساختار نود

```yaml
---
id: {node_id}
title: {title}
layer: Founder | PreLaunch | Launch | Future | Meta
domain: FND | LEG | BRD | FIN | STR | MKT | TEC | PLT | AI | OPS | HR | SEC | QA | RND | INT | CONV
status: draft
owner: احمد فیروزمندی بندپی
created: YYYY-MM-DD
version: 0.1.0
dependencies: []
tags: []
---
```

## ۷ بخش نود

---
۱. هدف (Why)
۲. محتوا
۳. اقدامات
۴. خروجی (Deliverable)
۵. ریسک‌ها
۶. ارجاعات
۷. Changelog

---


## مراحل ساخت نود جدید

## ۱. بررسی وجود نود

notes.search({ query: "{node_id}", limit: 5 })

## ۲. دریافت اطلاعات از کاربر
ID (مثلاً FND-009)

Title

Layer

Domain

محتوای ۷ بخش

## ۳. ساخت فایل

notes.create({
  path: "{layer_folder}/{node_id} — {title}.md",
  content: "{frontmatter + 7 sections}"
})

نکته: layer_folder بر اساس layer انتخاب می‌شود:

Founder → 01_Founder/

PreLaunch → 02_PreLaunch/

Launch → 03_Launch/

Future → 04_Future/

Meta → 00_Meta/

## ۴. لینک‌دهی
به نودهای مرتبط: [[FND-XXX]]

به Integration: [[3.1-semantic-search-api]]

### مراحل بروزرسانی نود موجود
## ۱. خواندن نود فعلی

```text
notes.read({ path: "{path}" })
```

## ۲. تشخیص بخش‌های نیازمند بروزرسانی
کدام بخش باید تغییر کند؟

آیا بخش جدید اضافه شود؟

## ۳. بروزرسانی frontmatter

notes.update_frontmatter({
  path: "{path}",
  updates: { status: "review", version: "0.2.0" }
})

## ۴. افزودن بخش جدید (اگر لازم)

notes.append({
  path: "{path}",
  content: "## ۸. بخش جدید\n..."
})

## ۵. افزودن Changelog

notes.append({
  path: "{path}",
  content: "- v0.2.0 (YYYY-MM-DD): بروزرسانی ..."
})

## مثال
ورودی: "نود FND-009 با عنوان 'تجربه تست اتوماسیون' بساز. Layer: Founder، Domain: FND."

خروجی:
۱. بررسی: FND-009 وجود ندارد
۲. سوال: "اطلاعات ۷ بخش را بدهید"
۳. ساخت: 01_Founder/FND-009 — تجربه تست اتوماسیون.md
۴. تأیید: "آیا ساخته شود؟"
۵. ساخت با MCP Obsidian

## قواعد
✅ همیشه:

از node-template.md استفاده کن

به نودهای مرتبط لینک بده

از کاربر تأیید بگیر

version را در بروزرسانی افزایش بده

❌ هرگز:

بدون تأیید کاربر نود نساز

frontmatter را ناقص نگذار

Changelog را فراموش نکن

