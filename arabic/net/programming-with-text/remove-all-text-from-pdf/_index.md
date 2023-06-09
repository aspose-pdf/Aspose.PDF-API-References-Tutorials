---
title: قم بإزالة كل النص من PDF
linktitle: قم بإزالة كل النص من PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إزالة كل النص من مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 290
url: /ar/net/programming-with-text/remove-all-text-from-pdf/
---

 في هذا البرنامج التعليمي ، سنشرح كيفية إزالة كل النص من مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنمر بعملية فتح ملف PDF خطوة بخطوة باستخدام ملف`TextFragmentAbsorber` لإزالة كل النص وحفظ ملف PDF المعدل باستخدام كود المصدر C # المقدم.

## متطلبات

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي لبرمجة C #.

## الخطوة 1: قم بإعداد دليل المستندات

 أولاً ، تحتاج إلى تعيين المسار إلى الدليل حيث توجد ملفات PDF الخاصة بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى ملفات PDF الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

 بعد ذلك ، نفتح مستند PDF باستخدام ملف`Document` فئة من مكتبة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## الخطوة 3: إزالة كل النص

 نقوم بتهيئة ملف`TextFragmentAbsorber` كائن واستخدمه لإزالة كل النص الممتص من مستند PDF.

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## الخطوة 4: احفظ ملف PDF المعدل

أخيرًا ، نقوم بحفظ مستند PDF المعدل في ملف الإخراج المحدد.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### عينة من التعليمات البرمجية المصدر لـ Remove All Text From PDF باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// بدء TextFragmentAbsorber
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
// قم بإزالة كل النص الممتص
absorber.RemoveAllText(pdfDocument);
// احفظ المستند
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إزالة كل النص من مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك فتح ملف PDF وإزالة كل النص باستخدام`TextFragmentAbsorber`، وحفظ ملف PDF المعدل.