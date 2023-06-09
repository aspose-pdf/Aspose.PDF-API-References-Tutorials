---
title: تحويل منطقة الصفحة إلى DOM
linktitle: تحويل منطقة الصفحة إلى DOM
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل منطقة معينة من صفحة PDF بسهولة إلى نموذج كائن المستند (DOM) باستخدام Aspose.PDF for .NET.
type: docs
weight: 80
url: /ar/net/programming-with-images/convert-page-region-to-dom/
---

سيأخذك هذا الدليل خطوة بخطوة حول كيفية تحويل منطقة معينة من الصفحة إلى Document Object Model (DOM) باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل أن تبدأ ، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

 في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## الخطوة 3: احصل على مستطيل منطقة الصفحة

 في هذه الخطوة ، سنقوم بتعريف مستطيل يمثل المنطقة المحددة من الصفحة التي نريد تحويلها إلى DOM. استخدم ال`Aspose.Pdf.Rectangle` فئة لتحديد إحداثيات المستطيل.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## الخطوة 4: تحديد منطقة اقتصاص الصفحة

 استخدم ال`CropBox` ممتلكات`Page` لتعيين مربع اقتصاص الصفحة إلى مستطيل المنطقة المطلوب.

```csharp
document.Pages[1].CropBox = pageRect;
```

## الخطوة 5: احفظ مستند PDF الذي تم اقتصاصه في دفق

 في هذه الخطوة ، سنحفظ مستند PDF الذي تم اقتصاصه في دفق باستخدام امتداد`MemoryStream` فصل.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## الخطوة 6: افتح مستند PDF الذي تم اقتصاصه وقم بتحويله إلى صورة

 افتح مستند PDF الذي تم اقتصاصه باستخدام ملف`Document` فئة وتحويلها إلى صورة. سوف نستخدم دقة 300 نقطة في البوصة.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## الخطوة 7: تحويل الصفحة المحددة إلى صورة

 قم بتحويل الصفحة المحددة إلى صورة باستخدام ملف`Process` طريقة`pngDevice` هدف. حدد مسار إخراج الصورة.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### نموذج التعليمات البرمجية المصدر لتحويل منطقة الصفحة إلى DOM باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document document = new Document( dataDir + "AddImage.pdf");
// احصل على مستطيل لمنطقة صفحة معينة
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
//قم بتعيين قيمة CropBox حسب مستطيل منطقة الصفحة المطلوبة
document.Pages[1].CropBox = pageRect;
// حفظ المستند الذي تم اقتصاصه في الدفق
MemoryStream ms = new MemoryStream();
document.Save(ms);
// افتح مستند PDF الذي تم اقتصاصه وقم بالتحويل إلى صورة
document = new Document(ms);
// إنشاء كائن القرار
Resolution resolution = new Resolution(300);
// قم بإنشاء جهاز PNG بسمات محددة
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// قم بتحويل صفحة معينة وحفظ الصورة للدفق
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## خاتمة

تهنئة ! لقد نجحت في تحويل منطقة معينة من الصفحة إلى نموذج كائن المستند (DOM) باستخدام Aspose.PDF لـ .NET. يتم حفظ الصورة الناتجة في الدليل المحدد. يمكنك الآن استخدام هذه الصورة في مشاريعك أو تطبيقاتك.