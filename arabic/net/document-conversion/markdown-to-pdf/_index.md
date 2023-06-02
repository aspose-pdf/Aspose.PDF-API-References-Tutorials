---
title: تخفيض السعر إلى PDF
linktitle: تخفيض السعر إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل Markdown إلى PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 60
url: /ar/net/document-conversion/markdown-to-pdf/
---

في هذا البرنامج التعليمي ، سنرشدك خلال عملية تحويل ملف Markdown إلى PDF باستخدام Aspose.PDF لـ .NET. Markdown هي لغة ترميز خفيفة الوزن تستخدم لتنسيق نص عادي بطريقة منظمة. باتباع الخطوات أدناه ، ستتمكن من تحويل ملفات Markdown إلى تنسيق PDF.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل ملف Markdown
في هذه الخطوة سنقوم بتحميل ملف Markdown باستخدام Aspose.PDF for .NET. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح مستند Markdown
Document doc = new Document(dataDir + "sample.md", new MdLoadOptions());
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"`مع الدليل الفعلي حيث يوجد ملف Markdown الخاص بك.

## الخطوة 2: تخفيض السعر إلى تحويل PDF
بعد تحميل ملف Markdown ، يمكننا متابعة التحويل إلى PDF. استخدم الكود التالي:

```csharp
// احفظ المستند بتنسيق PDF
doc.Save(dataDir + "MarkdownToPDF.pdf");
```

 يحول الكود أعلاه ملف Markdown إلى تنسيق PDF ويحفظه كاسم ملف`"MarkdownToPDF.pdf"`.

### مثال على شفرة المصدر لـ Markdown إلى PDF باستخدام Aspose.Words for .NET


```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح مستند Markdown
Document doc = new Document(dataDir + "sample.md", new MdLoadOptions());
// احفظ المستند بتنسيق PDF
doc.Save(dataDir + "MarkdownToPDF.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتحويل ملف Markdown إلى PDF باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون الآن قادرًا على تحويل ملفات Markdown إلى تنسيق PDF. يمكن أن تكون هذه الميزة مفيدة عندما تحتاج إلى إنشاء مستندات PDF من محتوى Markdown.