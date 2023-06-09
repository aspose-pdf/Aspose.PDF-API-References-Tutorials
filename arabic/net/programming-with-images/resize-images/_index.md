---
title: تغيير حجم الصور
linktitle: تغيير حجم الصور
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتغيير حجم الصور في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 250
url: /ar/net/programming-with-images/resize-images/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تغيير حجم الصور في مستند PDF باستخدام Aspose.PDF for .NET. اتبع هذه الخطوات لإجراء هذه العملية بسهولة.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي بيئة تطوير أخرى مثبتة ومهيأة.
- معرفة أساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## الخطوة 1: تحميل مستند PDF

للبدء ، استخدم الكود التالي لتحميل مستند PDF:

```csharp
// تهيئة الوقت
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

تأكد من توفير المسار الصحيح لوثيقة PDF الخاصة بك.

## الخطوة 2: تهيئة خيارات التحسين

قبل تغيير حجم الصور ، نحتاج إلى تهيئة خيارات التحسين. استخدم الكود التالي:

```csharp
// تهيئة OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// قم بتنشيط خيار CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// ضبط جودة الصورة
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// قم بتنشيط خيار ResizeImages
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// تعيين الدقة القصوى
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

يمكنك ضبط إعدادات التحسين وفقًا لاحتياجاتك.

## الخطوة 3: تحسين مستند PDF

سنقوم الآن بتحسين مستند PDF باستخدام خيارات التحسين التي حددناها. استخدم الكود التالي:

```csharp
// قم بتحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

تأكد من توفير المسار المطلوب واسم الملف لمستند PDF المحدث.

### نموذج التعليمات البرمجية المصدر لتغيير حجم الصور باستخدام Aspose.PDF لـ .NET 
```csharp
// تهيئة الوقت
var time = DateTime.Now.Ticks;
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// تهيئة OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// قم بتعيين خيار CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// تعيين خيار ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// تعيين خيار ResizeImage
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// تعيين خيار MaxResolution
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لقد نجحت في تغيير حجم الصور في مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لتغيير حجم الصور في ملفات PDF.