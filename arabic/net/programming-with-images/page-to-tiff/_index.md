---
title: الصفحة إلى TIFF
linktitle: الصفحة إلى TIFF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل صفحة PDF إلى TIFF باستخدام Aspose.PDF for .NET.
type: docs
weight: 230
url: /ar/net/programming-with-images/page-to-tiff/
---

في هذا البرنامج التعليمي ، سنوجهك خلال عملية تحويل صفحة PDF إلى تنسيق TIFF باستخدام Aspose.PDF لـ .NET. Aspose.PDF هي مكتبة قوية تسمح للمطورين بالعمل مع مستندات PDF برمجيًا. باتباع هذا الدليل خطوة بخطوة ، ستتمكن من تحويل صفحة PDF إلى TIFF دون عناء.

## متطلبات

قبل أن نبدأ ، تأكد من توفر لديك ما يلي:

- تثبيت وتكوين Visual Studio أو أي IDE مفضل آخر.
- فهم أساسي للغة البرمجة C #.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي.

الآن ، دعنا نتعمق في عملية تحويل صفحة PDF إلى TIFF باستخدام Aspose.PDF لـ .NET.

## الخطوة 1: إعداد Aspose.PDF لـ .NET

للبدء ، اتبع الخطوات التالية:

1. قم بإنشاء مشروع C # جديد في IDE المفضل لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET في مشروعك.
3. استيراد مساحات الأسماء الضرورية:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using Aspose.Pdf.Resolution;
using Aspose.Pdf.Types;
```

## الخطوة 2: تحميل مستند PDF

لتحويل صفحة PDF إلى TIFF ، تحتاج أولاً إلى تحميل مستند PDF. استخدم الكود التالي:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

تأكد من توفير المسار الصحيح لمستند PDF الخاص بك.

## الخطوة 3: إنشاء كائنات الدقة و TiffSettings

 بعد ذلك ، نحتاج إلى إنشاء ملف`Resolution` كائن و`TiffSettings` هدف. تحدد هذه الكائنات الدقة والإعدادات لصورة TIFF. استخدم الكود التالي:

```csharp
// إنشاء كائن القرار
Resolution resolution = new Resolution(300);

// إنشاء كائن TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
```

اضبط الدقة والإعدادات الأخرى وفقًا لمتطلباتك.

## الخطوة 4: إنشاء TiffDevice

 لإجراء التحويل ، نحتاج إلى إنشاء ملف`TiffDevice` هدف. هذا الجهاز سوف يتعامل مع عملية التحويل. استخدم الكود التالي:

```csharp
// قم بإنشاء جهاز TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## الخطوة 5: تحويل صفحة PDF إلى TIFF

حان الوقت الآن لتحويل صفحة PDF إلى TIFF. يمكننا تحويل صفحة معينة بتحديد رقم الصفحة. في هذا المثال ، سنقوم بتحويل الصفحة الأولى. استخدم الكود التالي:

```csharp
// قم بتحويل صفحة معينة وحفظ الصورة في دفق
tiffDevice.Process(pdfDocument, 1, 1, dataDir + "PageToTIFF_out.tif");
```

 يستبدل`1, 1` مع نطاق الصفحات المطلوب إذا كنت تريد تحويل صفحات متعددة.

## الخطوة 6: حفظ صورة TIFF



بمجرد اكتمال التحويل ، نحتاج إلى حفظ صورة TIFF في الموقع المطلوب. استخدم الكود التالي:

```csharp
tiffDevice.Process(pdfDocument, 1, 1, dataDir + "PageToTIFF_out.tif");
```

تأكد من توفير مسار ملف الإخراج الصحيح.

## الخطوة 7: إنهاء التحويل

بعد حفظ صورة TIFF ، يمكننا عرض رسالة نجاح للإشارة إلى التحويل الناجح. استخدم الكود التالي:

```csharp
System.Console.WriteLine("PDF one page converted to TIFF successfully!");
```

تهانينا! لقد نجحت في تحويل صفحة PDF إلى TIFF باستخدام Aspose.PDF لـ .NET.

### نموذج التعليمات البرمجية المصدر لـ Page To TIFF باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
// إنشاء كائن القرار
Resolution resolution = new Resolution(300);
// إنشاء كائن TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
// قم بإنشاء جهاز TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// قم بتحويل صفحة معينة وحفظ الصورة للدفق
tiffDevice.Process(pdfDocument, 1, 1, dataDir + "PageToTIFF_out.tif");
System.Console.WriteLine("PDF one page converted to tiff successfully!");
```

## خاتمة

في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتحويل صفحة PDF إلى TIFF باستخدام Aspose.PDF لـ .NET. بدأنا بإعداد المتطلبات الأساسية اللازمة ، بما في ذلك تثبيت Aspose.PDF لـ .NET وتكوين بيئة التطوير الخاصة بك. بعد ذلك ، مررنا بكل خطوة ، من تحميل مستند PDF إلى حفظ صورة TIFF.