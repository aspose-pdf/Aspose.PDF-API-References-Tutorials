---
title: صور الانكماش السريع
linktitle: صور الانكماش السريع
second_title: Aspose.PDF لمرجع .NET API
description: تقليل حجم الصور في ملف PDF بسرعة باستخدام Aspose.PDF for .NET.
type: docs
weight: 130
url: /ar/net/programming-with-images/fast-shrink-images/
---

سيأخذك هذا الدليل خطوة بخطوة حول كيفية تقليل حجم الصور بسرعة في ملف PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تهيئة الوقت

قبل أن نبدأ ، سنقوم بتهيئة الوقت لقياس أداء الضغط. أضف الكود التالي لتسجيل وقت البدء:

```csharp
var time = DateTime.Now.Ticks;
```

## الخطوة 2: تحديد دليل المستند

 تأكد من تعيين دليل المستند الصحيح. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

 في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## الخطوة 4: تهيئة خيارات التحسين

 في هذه الخطوة ، سنقوم بتهيئة خيارات التحسين لضغط الصور. قم بإنشاء مثيل لـ`OptimizationOptions` وحدد الخيارات المناسبة. في هذا المثال ، نقوم بتمكين ضغط الصور ، وضبط جودة الصورة على 75 ، واستخدام إصدار الضغط السريع.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## الخطوة 5: تحسين مستند PDF

 في هذه الخطوة ، سنقوم بتحسين مستند PDF باستخدام خيارات التحسين المحددة مسبقًا. اتصل ب`OptimizeResources` طريقة`pdfDocument` كائن وتمرير خيارات التحسين.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## الخطوة 6: احفظ مستند PDF المحدث

 احفظ مستند PDF المحدث باستخدام ملف`Save` طريقة`pdfDocument` هدف. حدد مسار الإخراج لملف PDF.

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### عينة من التعليمات البرمجية المصدر لـ Fast Shrink Images باستخدام Aspose.PDF لـ .NET 
```csharp
// تهيئة الوقت
var time = DateTime.Now.Ticks;
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// تهيئة OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// قم بتعيين خيار CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// تعيين خيار ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
// قم بتعيين إصدار ضغط Imagae على السرعة
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لقد قمت بسرعة بتقليل حجم الصور في ملف PDF باستخدام Aspose.PDF لـ .NET. يتم حفظ ملف PDF المحسن في الدليل المحدد. يمكنك الآن استخدام ملف PDF هذا مع صور مخفضة للحصول على احتياجات تخزين أو مشاركة أكثر كفاءة.