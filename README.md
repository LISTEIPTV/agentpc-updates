# Agent PC MOROCCARE — update feed

هاد الـ repo هو **مصدر التحديثات** ديال تطبيق Agent PC MOROCCARE.

- `version.json` — الـ manifest اللي كيقراه التطبيق عند Hicham:
  `{ version, exeUrl, sha256, notes }`
- الملف التنفيذي الجديد `AgentPC.exe` كيتنشر كـ **Release asset**
  (مثلاً: tag `v1.1.0` ← `…/releases/download/v1.1.0/AgentPC.exe`)،
  و `version.json` كيشير ليه بـ `exeUrl` مع الـ `sha256` ديالو.

التطبيق كيقارن النسخة: إلا كانت أجدد → كيعرض «تحديث جديد» بالملاحظات،
وإلا وافق Hicham كيحمّل الملف، كيتحقق من SHA256، كيبدل راسو بوحدو
وكيعاود يبدا. النشر كيتم من عند Elhour بـ:

```bash
tools/publish-update.sh <version> "<release notes>"
```

(من داخل مجلد Agent-PC-V1 — التفاصيل في BUILD-REPORT-UPDATE.md.)
