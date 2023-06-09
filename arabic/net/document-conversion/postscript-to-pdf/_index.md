---
title: بوستسكريبت إلى PDF
linktitle: بوستسكريبت إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل PostScript إلى PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 230
url: /ar/net/document-conversion/postscript-to-pdf/
---

في هذا البرنامج التعليمي ، سنرشدك خلال عملية تحويل ملف PostScript (PS) إلى تنسيق PDF باستخدام Aspose.PDF لـ .NET. تنسيق PostScript هو لغة وصف الصفحة المستخدمة لوصف المظهر الرسومي للمستندات. باتباع الخطوات أدناه ، ستتمكن من تحويل ملف PostScript إلى تنسيق PDF.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل مستند PostScript
في هذه الخطوة سنقوم بتحميل ملف PostScript المصدر باستخدام Aspose.PDF for .NET. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء مثيل جديد من PsLoadOptions
LoadOptions options = new PsLoadOptions();

// افتح مستند .ps مع إنشاء خيارات التحميل
Document pdfDocument = new Document(dataDir + "input.ps", options);
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف PostScript الخاص بك.

## الخطوة 2: حفظ ملف PDF الناتج
أخيرًا ، سنقوم بحفظ ملف PostScript المحول إلى PDF. استخدم الكود التالي:

```csharp
// احفظ المستند
pdfDocument.Save(dataDir + "PSToPDF.pdf");
```

 يحفظ الكود أعلاه ملف PostScript المحول بتنسيق PDF باسم الملف`"PSToPDF.pdf"`.

### مثال على شفرة المصدر لـ Postscript إلى PDF باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بإنشاء مثيل جديد من PsLoadOptions
LoadOptions options = new PsLoadOptions();
//افتح مستند .ps بخيارات التحميل التي تم إنشاؤها
Document pdfDocument = new Document(dataDir + "input.ps", options);
// احفظ المستند
pdfDocument.Save(dataDir + "PSToPDF.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتحويل ملف PostScript إلى تنسيق PDF باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون قادرًا الآن على تحويل ملف PostScript إلى تنسيق PDF. هذه الميزة مفيدة عندما تريد تحويل ملفات PostScript إلى تنسيق PDF لاستخدام أكثر شيوعًا وتوافق أفضل.