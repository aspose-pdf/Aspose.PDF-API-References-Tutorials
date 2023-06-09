---
title: ضغط فك ترميز Flate
linktitle: ضغط فك ترميز Flate
second_title: Aspose.PDF لمرجع .NET API
description: ضغط الصور بكفاءة في ملف PDF باستخدام ضغط Flate Decode مع Aspose.PDF for .NET.
type: docs
weight: 140
url: /ar/net/programming-with-images/flate-decode-compression/
---

سيأخذك هذا الدليل خطوة بخطوة حول كيفية ضغط الصور باستخدام ضغط Flate Decode في ملف PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 تأكد من تعيين دليل المستند الصحيح. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

 في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
Document doc = new Document(dataDir + "AddImage.pdf");
```

## الخطوة 3: تهيئة خيارات التحسين

 في هذه الخطوة ، سنقوم بتهيئة خيارات التحسين لضغط الصور. قم بإنشاء مثيل لـ`OptimizationOptions` وحدد الخيارات المناسبة. في هذا المثال ، نستخدم ضغط Flate Decode لتحسين الصور.

```csharp
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
```

## الخطوة 4: تحسين مستند PDF

 في هذه الخطوة ، سنقوم بتحسين مستند PDF باستخدام خيارات التحسين المحددة مسبقًا. اتصل ب`OptimizeResources` طريقة`doc` كائن وتمرير خيارات التحسين.

```csharp
doc.OptimizeResources(optimizationOptions);
```

## الخطوة 5: احفظ مستند PDF المحدث

 احفظ مستند PDF المحدث باستخدام ملف`Save` طريقة`doc` هدف. حدد مسار الإخراج لملف PDF.

```csharp
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

### نموذج التعليمات البرمجية المصدر لضغط فك ترميز Flate باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document doc = new Document(dataDir + "AddImage.pdf");
// تهيئة OptimizationOptions
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
//لتحسين الصورة باستخدام FlateDecode Compression ، اضبط خيارات التحسين على Flate
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
// تعيين خيارات التحسين
doc.OptimizeResources(optimizationOptions);
// حفظ المستند
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

## خاتمة

تهنئة ! لقد نجحت في ضغط الصور في ملف PDF باستخدام ضغط Flate Decode مع Aspose.PDF for .NET. يتم حفظ ملف PDF المحسن في الدليل المحدد. يمكنك الآن استخدام ملف PDF هذا للحصول على احتياجات تخزين أو مشاركة أكثر كفاءة.