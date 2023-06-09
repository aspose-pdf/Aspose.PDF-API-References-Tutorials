---
title: تقليص الصور
linktitle: تقليص الصور
second_title: Aspose.PDF لمرجع .NET API
description: دليل تفصيلي خطوة بخطوة لتقليل حجم الصور في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 280
url: /ar/net/programming-with-images/shrink-images/
---

في هذا البرنامج التعليمي ، سنخبرك بكيفية تقليل حجم الصور في مستند PDF باستخدام Aspose.PDF لـ .NET. اتبع هذه الخطوات لإجراء هذه العملية بسهولة.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي بيئة تطوير أخرى مثبتة ومهيأة.
- معرفة أساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## الخطوة 1: تحميل مستند PDF

للبدء ، استخدم الكود التالي لتحميل مستند PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

تأكد من توفير المسار الصحيح لوثيقة PDF الخاصة بك.

## الخطوة 2: تهيئة خيارات التحسين

بعد ذلك ، سنقوم بتهيئة خيارات التحسين لتقليل حجم الصور. استخدم الكود التالي:

```csharp
// تهيئة OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// قم بتنشيط خيار CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// ضبط جودة الصورة
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
```

يمكنك ضبط إعدادات التحسين وفقًا لاحتياجاتك.

## الخطوة 3: تحسين مستند PDF

سنقوم الآن بتحسين مستند PDF عن طريق تقليل حجم الصور. استخدم الكود التالي:

```csharp
// قم بتحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "Shrinkimage_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages successfully reduced.\nFile saved as: " + dataDir);
```

تأكد من توفير المسار المطلوب واسم الملف لمستند PDF المحدث.

### عينة من التعليمات البرمجية المصدر لـ Shrink Images باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// تهيئة OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// قم بتعيين خيار CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// تعيين خيار ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "Shrinkimage_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage shrinked successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لقد نجحت في تقليل حجم الصور في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لتحسين حجم الصور في ملفات PDF.