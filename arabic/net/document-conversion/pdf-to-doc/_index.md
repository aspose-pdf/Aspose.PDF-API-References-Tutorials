---
title: PDF إلى DOC
linktitle: PDF إلى DOC
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل PDF إلى DOC باستخدام Aspose.PDF for .NET.
type: docs
weight: 110
url: /ar/net/document-conversion/pdf-to-doc/
---

في هذا البرنامج التعليمي ، سنوجهك خلال عملية تحويل ملف PDF إلى تنسيق DOC باستخدام Aspose.PDF لـ .NET. تُستخدم ملفات PDF بشكل شائع لعرض المستندات ومشاركتها عالميًا ، بينما تنسيق DOC خاص بـ Microsoft Word. باتباع الخطوات أدناه ، ستتمكن من تحويل ملفات PDF إلى تنسيق DOC.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: فتح ملف PDF المصدر
في هذه الخطوة ، سنفتح ملف PDF المصدر باستخدام Aspose.PDF لـ .NET. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح مستند PDF المصدر
Document pdfDocument = new Document(dataDir + "PDFToDOC.pdf");
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف PDF الخاص بك.

## الخطوة 2: تحويل PDF إلى تنسيق DOC
بعد فتح ملف PDF ، يمكننا متابعة التحويل إلى تنسيق DOC. استخدم الكود التالي:

```csharp
// احفظ الملف بتنسيق مستند MS
pdfDocument.Save(dataDir + "PDFToDOC_out.doc", SaveFormat.Doc);
```

 يحول الكود أعلاه ملف PDF إلى تنسيق DOC ويحفظه كاسم ملف`"PDFToDOC_out.doc"`.

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع الدليل المطلوب حيث تريد حفظ ملف DOC الناتج.

### مثال على كود المصدر لـ PDF إلى DOC باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";          

// افتح مستند PDF المصدر
Document pdfDocument = new Document(dataDir + "PDFToDOC.pdf");

//احفظ الملف بتنسيق مستند MS
pdfDocument.Save(dataDir + "PDFToDOC_out.doc", SaveFormat.Doc);
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتحويل ملف PDF إلى تنسيق DOC باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون الآن قادرًا على تحويل ملفات PDF إلى تنسيق DOC. يمكن أن تكون هذه الميزة مفيدة عندما تحتاج إلى العمل مع ملفات PDF في Microsoft Word أو التطبيقات الأخرى التي تدعم تنسيق DOC.