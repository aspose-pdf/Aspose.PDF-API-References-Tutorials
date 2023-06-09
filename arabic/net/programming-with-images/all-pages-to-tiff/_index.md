---
title: جميع الصفحات إلى TIFF
linktitle: جميع الصفحات إلى TIFF
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل جميع صفحات مستند PDF إلى ملف TIFF باستخدام Aspose.PDF for .NET.
type: docs
weight: 20
url: /ar/net/programming-with-images/all-pages-to-tiff/
---

سيأخذك هذا الدليل خطوة بخطوة حول كيفية تحويل جميع صفحات مستند PDF إلى ملف TIFF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل أن تبدأ ، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

 في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## الخطوة 3: إنشاء كائن القرار

 إنشاء`Resolution` لتعيين دقة صورة TIFF. في هذا المثال ، نستخدم دقة 300 نقطة في البوصة.

```csharp
Resolution resolution = new Resolution(300);
```

## الخطوة 4: قم بإنشاء كائن TiffSettings

 إنشاء`TiffSettings` لتحديد إعدادات ملف TIFF الناتج. في هذا المثال ، نقوم بإيقاف الضغط ، واستخدام عمق اللون الافتراضي ، وضبط الشكل على الوضع الأفقي.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
```

## الخطوة 5: قم بإنشاء جهاز TIFF

 قم بإنشاء جهاز TIFF باستخدام ملف`TiffDevice` كائن ، مع تحديد الدقة وإعدادات TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## الخطوة 6: تحويل جميع الصفحات وحفظ الصورة

 استخدم ال`Process` طريقة جهاز TIFF لتحويل كل صفحات مستند PDF وحفظ الصورة في ملف TIFF. حدد مسار إخراج الملف.

```csharp
tiffDevice.Process(pdfDocument, dataDir + "AllPagesToTIFF_out.tif");
System.Console.WriteLine("PDF all pages converted to one tiff file successfully!");
```

### نموذج التعليمات البرمجية المصدر لجميع الصفحات إلى TIFF باستخدام Aspose.PDF لـ .NET 
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
tiffDevice.Process(pdfDocument, dataDir + "AllPagesToTIFF_out.tif");
System.Console.WriteLine("PDF all pages converted to one tiff file successfully!");
```

## خاتمة

تهنئة ! لقد نجحت في تحويل جميع صفحات مستند PDF إلى ملف TIFF باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام ملف TIFF الذي تم إنشاؤه في مشاريعك أو تطبيقاتك.