---
title: PDF إلى EPUB
linktitle: PDF إلى EPUB
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل PDF إلى EPUB باستخدام Aspose.PDF for .NET.
type: docs
weight: 120
url: /ar/net/document-conversion/pdf-to-epub/
---

في هذا البرنامج التعليمي ، سنوجهك خلال عملية تحويل ملف PDF إلى تنسيق EPUB باستخدام Aspose.PDF لـ .NET. يتم استخدام تنسيق PDF بشكل شائع لعرض المستندات ، بينما تم تصميم تنسيق EPUB خصيصًا للكتب الإلكترونية. باتباع الخطوات أدناه ، ستتمكن من تحويل ملفات PDF إلى تنسيق EPUB.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل مستند PDF
في هذه الخطوة ، سنقوم بتحميل ملف PDF باستخدام Aspose.PDF for .NET. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل مستند PDF
Document pdfDocument = new Document(dataDir + "PDFToEPUB.pdf");
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف PDF الخاص بك.

## الخطوة 2: إنشاء خيارات حفظ EPUB
بعد تحميل مستند PDF ، سنقوم بإنشاء مثيل لخيارات الحفظ لتنسيق EPUB. استخدم الكود التالي:

```csharp
// إنشاء خيارات النسخ الاحتياطي لـ EPUB
EpubSaveOptions options = new EpubSaveOptions();
```

## الخطوة 3: تحديد تخطيط المحتوى
سنقوم الآن بتحديد تخطيط محتويات كتاب EPUB. استخدم الكود التالي:

```csharp
// مواصفات تخطيط المحتويات
options.ContentRecognitionMode = EpubSaveOptions.RecognitionMode.Flow;
```

## الخطوة 4: حفظ مستند EPUB
بمجرد تكوين خيارات الحفظ ، يمكننا الآن حفظ ملف EPUB الناتج. هذه هي الخطوة الأخيرة:

```csharp
// احفظ مستند EPUB
pdfDocument.Save(dataDir + "PDFToEPUB_out.epub", options);
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع الدليل المطلوب حيث تريد حفظ ملف EPUB الناتج.

### مثال على شفرة المصدر لـ PDF إلى EPUB باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل مستند PDF
Document pdfDocument = new Document(dataDir + "PDFToEPUB.pdf");

// إنشاء خيارات حفظ Epub
EpubSaveOptions options = new EpubSaveOptions();

// حدد تخطيط المحتويات
options.ContentRecognitionMode = EpubSaveOptions.RecognitionMode.Flow;

// احفظ مستند ePUB
pdfDocument.Save(dataDir + "PDFToEPUB_out.epub", options);
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتحويل ملف PDF بتنسيق EPUB باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات أعلاه ، يمكنك بسهولة تحويل ملفات PDF إلى تنسيق EPUB. هذه الميزة مفيدة بشكل خاص لتحويل مستندات PDF إلى كتب إلكترونية قابلة للقراءة على أجهزة مختلفة.