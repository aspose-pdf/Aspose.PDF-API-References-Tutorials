---
title: تحويل منطقة الصفحة إلى DOM
linktitle: تحويل منطقة الصفحة إلى DOM
second_title: Aspose.PDF لمرجع .NET API
description: يمكنك بسهولة تحويل منطقة معينة من صفحة PDF إلى نموذج كائن المستند (DOM) باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 80
url: /ar/net/programming-with-images/convert-page-region-to-dom/
---
سيأخذك هذا الدليل خطوة بخطوة حول كيفية تحويل منطقة معينة من الصفحة إلى نموذج كائن المستند (DOM) باستخدام Aspose.PDF لـ .NET. تأكد من أنك قمت بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود الذي يحتوي على المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

في هذه الخطوة، سنقوم بفتح مستند PDF باستخدام الملف`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ وتمرير المسار إلى وثيقة PDF.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## الخطوة 3: الحصول على مستطيل منطقة الصفحة

 في هذه الخطوة، سنحدد مستطيلًا يمثل المنطقة المحددة من الصفحة التي نريد تحويلها إلى DOM. استخدم ال`Aspose.Pdf.Rectangle` فئة لتحديد إحداثيات المستطيل.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## الخطوة 4: تحديد مساحة الاقتصاص في الصفحة

 استخدم ال`CropBox` ملكية`Page` كائن لتعيين مربع القطع الخاص بالصفحة على مستطيل المنطقة المطلوبة.

```csharp
document.Pages[1].CropBox = pageRect;
```

## الخطوة 5: احفظ مستند PDF الذي تم اقتصاصه في دفق

 في هذه الخطوة، سنقوم بحفظ مستند PDF الذي تم اقتصاصه في دفق باستخدام الملف`MemoryStream` فصل.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## الخطوة 6: افتح مستند PDF الذي تم اقتصاصه وقم بتحويله إلى صورة

 افتح مستند PDF الذي تم اقتصاصه باستخدام الملف`Document` فئة وتحويلها إلى صورة. سوف نستخدم دقة 300 نقطة في البوصة.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## الخطوة 7: تحويل الصفحة المحددة إلى صورة

 تحويل الصفحة المحددة إلى صورة باستخدام`Process` طريقة`pngDevice`هدف. تحديد مسار إخراج الصورة.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### نموذج التعليمات البرمجية المصدر لتحويل منطقة الصفحة إلى DOM باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document document = new Document( dataDir + "AddImage.pdf");
// الحصول على مستطيل لمنطقة صفحة معينة
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
// قم بتعيين قيمة CropBox حسب مستطيل منطقة الصفحة المطلوبة
document.Pages[1].CropBox = pageRect;
// حفظ المستند الذي تم اقتصاصه في الدفق
MemoryStream ms = new MemoryStream();
document.Save(ms);
// افتح مستند PDF الذي تم اقتصاصه وقم بتحويله إلى صورة
document = new Document(ms);
// إنشاء كائن القرار
Resolution resolution = new Resolution(300);
// قم بإنشاء جهاز PNG بالسمات المحددة
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
//تحويل صفحة معينة وحفظ الصورة للبث
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## خاتمة

تهنئة ! لقد نجحت في تحويل منطقة معينة من الصفحة إلى نموذج كائن المستند (DOM) باستخدام Aspose.PDF لـ .NET. يتم حفظ الصورة الناتجة في الدليل المحدد. يمكنك الآن استخدام هذه الصورة في مشاريعك أو تطبيقاتك.

## الأسئلة الشائعة

#### س: ما هو الغرض من تحويل منطقة معينة من الصفحة إلى نموذج كائن المستند (DOM) باستخدام Aspose.PDF لـ .NET؟

ج: يمكن أن يكون تحويل منطقة معينة من صفحة PDF إلى نموذج كائن المستند (DOM) مفيدًا في استخراج قسم معين من المحتوى ومعالجته داخل مستند PDF.

#### س: كيف يسهل Aspose.PDF for .NET تحويل منطقة صفحة معينة إلى DOM؟

ج: يوفر Aspose.PDF for .NET عملية خطوة بخطوة لتحديد منطقة الصفحة المطلوبة، وتعيين منطقة الاقتصاص، وحفظ مستند PDF الذي تم اقتصاصه في دفق، وتحويل منطقة الصفحة المحددة إلى صورة.

#### س: لماذا من المهم تحديد دليل المستند قبل بدء عملية التحويل؟

ج: يضمن تحديد دليل المستند أن يكون مستند PDF والصورة الناتجة موجودين بشكل صحيح في مسار الإخراج المطلوب.

####  س: كيف`Document` class in Aspose.PDF for .NET help in the conversion process?

 ج: ال`Document` يتيح لك الفصل فتح مستندات PDF ومعالجتها وحفظها. في هذه الحالة، يتم استخدامه لتحميل مستند PDF وإنشاء نسخة مقصوصة منه.

####  س: ما هو الغرض من`Rectangle` class in the page region conversion process?

 ج: ال`Rectangle` تحدد الفئة إحداثيات المنطقة المحددة على صفحة PDF التي تريد تحويلها إلى DOM. يساعد في تحديد مساحة المحاصيل بدقة.

#### س: كيف يتم تعيين مساحة الاقتصاص في الصفحة على المنطقة المطلوبة في عملية التحويل؟

 ج: ال`CropBox` ملكية`Page` يتم استخدام الكائن لتعيين مساحة الاقتصاص للصفحة على المستطيل المحدد الذي يمثل المنطقة المحددة.

#### س: كيف يتم حفظ مستند PDF الذي تم اقتصاصه في التدفق أثناء عملية التحويل؟

 ج: يتم حفظ مستند PDF الذي تم اقتصاصه في ملف`MemoryStream` الكائن، والذي يسمح بالمعالجة الفعالة لمحتوى PDF.

####  س: ما هو الدور الذي يقوم به`PngDevice` class play in the page region to DOM conversion process?

 ج: ال`PngDevice` يساعد الفصل على تحويل مستند PDF الذي تم اقتصاصه إلى تنسيق صورة، مثل PNG، مما يسمح لك بتصور منطقة معينة من الصفحة.

#### س: هل يمكنني ضبط الدقة أو السمات الأخرى للصورة الناتجة أثناء عملية التحويل؟

 ج: نعم، يمكنك تعديل الدقة والسمات الأخرى للصورة الناتجة عن طريق تكوين`PngDevice` الكائن قبل تحويل الصفحة.