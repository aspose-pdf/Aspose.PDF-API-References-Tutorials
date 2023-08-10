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

 قم بتحويل الصفحة المحددة إلى صورة باستخدام ملف`Process` طريقة`pngDevice`هدف. حدد مسار إخراج الصورة.

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
// قم بتعيين قيمة CropBox حسب مستطيل منطقة الصفحة المطلوبة
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
//قم بتحويل صفحة معينة وحفظ الصورة للدفق
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## خاتمة

تهنئة ! لقد نجحت في تحويل منطقة معينة من الصفحة إلى نموذج كائن المستند (DOM) باستخدام Aspose.PDF لـ .NET. يتم حفظ الصورة الناتجة في الدليل المحدد. يمكنك الآن استخدام هذه الصورة في مشاريعك أو تطبيقاتك.

## التعليمات

#### س: ما هو الغرض من تحويل منطقة معينة من الصفحة إلى نموذج كائن المستند (DOM) باستخدام Aspose.PDF لـ .NET؟

ج: يمكن أن يكون تحويل منطقة معينة من صفحة PDF إلى Document Object Model (DOM) مفيدًا لاستخراج ومعالجة قسم معين من المحتوى داخل مستند PDF.

#### س: كيف يسهل Aspose.PDF لـ .NET تحويل منطقة صفحة معينة إلى DOM؟

ج: يوفر Aspose.PDF for .NET عملية خطوة بخطوة لتحديد منطقة الصفحة المطلوبة ، وتعيين منطقة الاقتصاص ، وحفظ مستند PDF الذي تم اقتصاصه إلى تدفق ، وتحويل منطقة الصفحة المحددة إلى صورة.

#### س: ما سبب أهمية تحديد دليل المستند قبل بدء عملية التحويل؟

ج: تحديد دليل الوثيقة يضمن أن وثيقة PDF والصورة الناتجة موجودة بشكل صحيح في مسار الإخراج المطلوب.

####  س: كيف يعمل ملف`Document` class in Aspose.PDF for .NET help in the conversion process?

 ج: إن`Document` تسمح لك class بفتح مستندات PDF ومعالجتها وحفظها. في هذه الحالة ، يتم استخدامه لتحميل مستند PDF وإنشاء نسخة مقصوصة منه.

####  س: ما هو الغرض من`Rectangle` class in the page region conversion process?

 ج: إن`Rectangle` تحدد class إحداثيات منطقة معينة على صفحة PDF التي تريد تحويلها إلى DOM. يساعد في تحديد منطقة المحاصيل بدقة.

#### س: كيف يتم تعيين مساحة المحاصيل في الصفحة على المنطقة المطلوبة في عملية التحويل؟

 ج: إن`CropBox` ممتلكات`Page` يتم استخدام الكائن لتعيين مساحة الاقتصاص من الصفحة على المستطيل المحدد الذي يمثل منطقة معينة.

#### س: كيف يتم حفظ مستند PDF الذي تم اقتصاصه في تدفق أثناء عملية التحويل؟

 ج: يتم حفظ مستند PDF الذي تم اقتصاصه في ملف`MemoryStream` كائن ، والذي يسمح بمعالجة فعالة لمحتوى PDF.

####  س: ما هو الدور الذي يقوم به`PngDevice` class play in the page region to DOM conversion process?

 ج: إن`PngDevice` تساعد class في تحويل مستند PDF الذي تم اقتصاصه إلى تنسيق صورة ، مثل PNG ، مما يتيح لك تصور منطقة الصفحة المحددة.

#### س: هل يمكنني ضبط الدقة أو السمات الأخرى للصورة الناتجة أثناء عملية التحويل؟

 ج: نعم ، يمكنك تعديل الدقة والسمات الأخرى للصورة الناتجة عن طريق تكوين ملف`PngDevice` كائن قبل تحويل الصفحة.