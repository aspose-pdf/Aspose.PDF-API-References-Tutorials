---
title: صورة CGM إلى PDF
linktitle: صورة CGM إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل صورة CGM إلى PDF بسهولة باستخدام Aspose.PDF for .NET.
type: docs
weight: 40
url: /ar/net/programming-with-images/cgm-image-to-pdf/
---

يوضح هذا الدليل التفصيلي كيفية تحويل صورة CGM إلى PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل أن تبدأ ، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد ملف CGM الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحديد ملف الإدخال والإخراج

 قم بتعيين اسم ملف إدخال CGM واسم ملف إخراج PDF. يستبدل`"corvette.cgm"` باسم ملف CGM الخاص بك ، وتحديث`dataDir`مع دليل الإخراج المطلوب واسم ملف PDF.

```csharp
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
```

## الخطوة 3: تحويل صورة CGM إلى PDF

 استخدم ال`Produce` طريقة`PdfProducer` لتحويل ملف CGM إلى تنسيق PDF باستخدام`ImportFormat.Cgm`. حدد ملف إدخال CGM وملف إخراج PDF.

```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```

### عينة من التعليمات البرمجية المصدر لـ CGMImage to PDF باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
// حفظ CGM في تنسيق PDF
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nCGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## خاتمة

تهنئة ! لقد نجحت في تحويل ملف CGM إلى PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام ملف PDF الذي تم إنشاؤه في مشاريعك أو تطبيقاتك.